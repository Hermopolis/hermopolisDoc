# RUN
参考
https://qiita.com/A-Kira/items/5aa0af261aacc4ce959e

```linux
docker-compose up -d 

http://127.0.0.1:8080


如果要修改端口
修改
docker-compose.yml 

  - "8080:8080"
  例如
    - "${你的端口号}:8080"

```

