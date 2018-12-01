# 몽고디비 설치 및 설정
[https://prezi.com/hwryjlcpmtby/google-cloud-platform-restful-api/]
- OS : ubuntu


## add the mongodb repository to /etc/apt/sources.list
~~~
sudo bash -c "echo 'deb http://downloads-distro.mongodb.org/repo/ubuntu-upstart dist 10gen' >> /etc/apt/sources.list"
~~~

## add 10gen's GPG key so that aptitude will trust the repository
~~~
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv 7F0CEB10
~~~

## Update aptitude's list of available packages
~~~
sudo apt-get update
~~~

## Install mongodb
~~~
sudo apt-get install mongodb-10gen
~~~

##+ vi /etc/mongodb.conf
~~~
logpath = /var/log/mongodb/mongod.log
#dbpath = /var/lib/mongodb/
dbpath = /data/databases/mongodb/
~~~
## use 'true' for options that don't take an argument
~~~
logappend = true
bind_ip = 127.0.0.1
auth = true
Doralab Server Team 
~~~


mongodb의 경우 데이터 폴더의 소유자:그룹이 mysql로 되어 있어 기동 불가.
databases를 root로 변경하고 mongodb는 mongodb:mongodb로 변경하여 정상 구동됨

## mongodb 계정 생성
mongodb 계정생성하는 부분이 빠져 있는것 같아 여기 적습니다.
~~~
bluedora@db7c3de1-f3ba-4f15-852c-5b8de948d78e:/data/www/api.doralab.co.kr$ mongo
MongoDB shell version: 2.4.8
connecting to: test
Welcome to the MongoDB shell.
For interactive help, type "help".
For more comprehensive documentation, see
http://docs.mongodb.org/
Questions? Try the support group
http://groups.google.com/group/mongodb-user

>
>
> use doralab;

switched to db doralab

>
>
~~~

## 몽고디비 설치 및 설정
~~~
> db.addUser('bluedora', 'ehfkehfk4%');
{
"user" : "bluedora",
"readOnly" : false,
"pwd" : "ac5374bf6c5f65d4247e266cc24f4ed1",
"_id" : ObjectId("52adc1c511c34642e8ecec55")
}
>
>
> exit

bye
~~~

bluedora@db7c3de1-f3ba-4f15-852c-5b8de948d78e:/data/www/api.doralab.co.kr$ mongo doralab;
MongoDB shell version: 2.4.8
connecting to: doralab
> db.auth('bluedora', 'ehfkehfk4%');

1

테스트
가입테스트 mysql 기록, mongodb기록 메일 발송 이상없음.
http://14.63.171.143/dla.auth.user.join


소스 수정사항.
143번 서버 소스에만 적용되어 있습니다.!!!!
test서버가 생성되어 자동으로 mysql, mongodb를 test서버를 바라보게 하였습니다.

server_info.js --> test서버 정보 추가

} else if (addresses == '172.27.202.105') {
server_info = 'test';

db.js --> test서버 정보 추가
} else if(si.server_info == 'test') { // real
host = 'localhost';
port = '3306';
user = 'bluedora';
password = 'ehfkehfk0)';
database = 'doralab';
}

mongodb.js --> test서버정보 추가
} else if(si.server_info == 'test') {
mg_ip = "localhost";

}


### MongoDB – 백업 및 복원

#### 백업 
~~~
mongodump --host {호스트주소} --port {포트번호} --db {타겟디비이름} --username {유저네임} --password {패스워드} --out {백업디렉토리} 
~~~

#### 복원
~~~ 
mongorestore --host {호스트주소} --port {포트번호} --db {타겟디비이름} --username {유저네임} --password {패스워드} {백업디렉토리} 
~~~

#### 몽고디비 실행
~~~
/usr/bin/mongod -f /etc/mongod.conf --fork
~~~

#### 몽고디비 종료
~~~
>use admin 
>db.shutdownServer();
server {
listen 80;
server_name api.tonginsys.com
client_max_body_size 100M;

access_log /data/logs/nginx/api.tonginsys.com/api.tonginsys.com.access.log;

location / {
add_header Access-Control-Allow-Origin *;
root /data/web/protoType/public;
index index.html;
expires 0d;
}

location /v1 {
add_header Access-Control-Allow-Origin *;
proxy_set_header X-Real-IP $remote_addr;
proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
proxy_set_header Host $http_host;
proxy_set_header X-NginX-Proxy true;

proxy_pass http://127.0.0.1:16001;
proxy_redirect off;
expires 0d;

## Compression
gzip on;
gzip_vary on;
gzip_static on;
gzip_buffers 16 8k;
gzip_comp_level 9;
gzip_http_version 1.0;
gzip_min_length 0;
gzip_types text/plain image/x-icon text/css application/json application/x-javascript text/xml application/xml application/xml+rss text/javascript;
}


}


server {
listen 443;
server_name api.tonginsys.com;

ssl on;
ssl_certificate /etc/nginx/ssl/api.doralab.co.kr_crt.pem;
ssl_certificate_key /etc/nginx/ssl/api.doralab.co.kr_key.pem;

ssl_session_timeout 5m;

ssl_protocols TLSv1 TLSv1.1 TLSv1.2;
ssl_ciphers ALL:!ADH:!EXPORT56:RC4+RSA:+HIGH:+MEDIUM:+LOW:+EXP;
ssl_prefer_server_ciphers on;

access_log /data/logs/nginx/ssl.tonginsys.com/ssl.tonginsys.com.access.log;
error_log /data/logs/nginx/ssl.tonginsys.com/ssl.tonginsys.com.error.log;

location / {
add_header Access-Control-Allow-Origin *;
proxy_set_header X-Real-IP $remote_addr;
proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
proxy_set_header Host $http_host;
proxy_set_header X-NginX-Proxy true;

root /data/web/protoType/public;
index index.html;
proxy_pass http://localhost:16001;
expires 0d;
}
~~~
