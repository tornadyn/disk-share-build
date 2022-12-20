# Dockerコンテナ　ディスク共有サンプル Volume

## priserv側はディスク共有する側、secserv側は共有してもらう側
### 実行例
>docker build  -t  myos1  -f Dockerfile1<br>
>docker build  -t  myos2  -f Dockerfile2<br>
>docker run  -dit  --name  priserv  myos1<br>
>docker run  -dit  --volumes-from  priserv --name  secserv myos2<br>

## 共有できているか確認
>docker  exec  -it  secserv  /bin/bash<br>
>cat  /data/greeting
