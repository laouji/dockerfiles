## dockerfiles

`docker build -t nginx_img_1 nginx/`
`docker run --name nginx_cont_1 --restart=always -p 80:80 -i -t nginx_img_1`
