#23：4e

docker container cp Nginx:/etc/nginx/nginx.conf C:\Users\Ksoul\Desktop\dev-ops\nginx\conf

docker container cp Nginx:/etc/nginx/conf.d/default.conf C:\Users\Ksoul\Desktop\dev-ops\nginx\conf\conf.d

docker container cp Nginx:/usr/share/nginx/html/index.html C:\Users\Ksoul\Desktop\dev-ops\nginx\html

docker run \
--name Nginx \
-p 80:80 \
-v C:\Users\Ksoul\Desktop\dev-ops\nginx\logs:/var/log/nginx \
-v C:\Users\Ksoul\Desktop\dev-ops\nginx\html:/usr/share/nginx/html \
-v C:\Users\Ksoul\Desktop\dev-ops\nginx\conf/nginx.conf:/etc/nginx/nginx.conf \
-v C:\Users\Ksoul\Desktop\dev-ops\nginx\conf/conf.d:/etc/nginx/conf.d \
-v C:\Users\Ksoul\Desktop\dev-ops\nginx\ssl:/etc/nginx/ssl/  \
--privileged=true -d --restart=always nginx