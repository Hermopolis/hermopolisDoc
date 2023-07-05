# RUN
vue-press docker-compose 一件部署


参考
https://qiita.com/A-Kira/items/5aa0af261aacc4ce959e


```linux
docker-compose up -d 

打开浏览器
http://127.0.0.1:8080

```
配置说明
docker-compose.yml 

```linux

version: '3.9'
services:
  vue-press:
    build: docker/vue-press  #构建目录
    ports:
      - "8080:8080"   #把电脑的8080->容器的8080 ，如果需要修改访问地址可以改成  "${你的端口}:8080" 
    volumes:
      - ./documents:/documents
    tty: true
    command: bash -c "yarn install && yarn docs:dev"
```
docker 构建参数
```linux
FROM node:16.0.0  #node的版本 
WORKDIR /documents 项目目录

RUN npm install -g npm@8.5.2
RUN npm cache clean -f
```