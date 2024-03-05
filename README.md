# docker-example-conf



<img width="768" alt="Screenshot 2024-03-05 alle 16 34 43" src="https://github.com/MrMagicalSoftware/docker-example-conf/assets/98833112/b789060b-95d2-4e68-9a36-2885fb9384b4">




```
version: '3.1'
 
services:
  db:
    image: mysql:latest
    container_name: db
    environment:
      MYSQL_ROOT_PASSWORD: Password1234!
      MYSQL_DATABASE: db
      MYSQL_USER: user
      MYSQL_PASSWORD: Password1234!
    ports:
      - "6033:3306"
 
  phpmyadmin:
    image: phpmyadmin
    restart: always
    ports:
      - 8080:80
    environment:
      - PMA_ARBITRARY=1
 
  ftp-server:
    container_name: my-ftp-server
    environment:
      - FTP_PASS=123
      - FTP_USER=user
    image: garethflowers/ftp-server
    ports:
      - '20-21:20-21/tcp'
      - '40000-40009:40000-40009/tcp'
    volumes:
          - '/data:/home/user'
```
