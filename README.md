# docker-example-conf




Pastebin
paste
Login Sign up
SHARE
TWEET
Guest User
Untitled
a guest
Mar 5th, 2024
1
0
23 hours
Not a member of Pastebin yet? Sign Up, it unlocks many cool features!
0.66 KB | None

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

create new paste  /  syntax languages  /  archive  /  faq  /  tools  /  night mode  /  api  /  scraping api  /  news  /  pro
privacy statement  /  cookies policy  /  terms of service /  security disclosure  /  dmca  /  report abuse  /  contact

By using Pastebin.com you agree to our cookies policy to enhance your experience.
Site design & logo © 2024 Pastebin
We use cookies for various purposes including analytics. By continuing to use Pastebin, you agree to our use of cookies as described in the Cookies Policy.  OK, I Understand
Not a member of Pastebin yet?
Sign Up, it unlocks many cool features!
 
