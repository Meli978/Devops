# Setup

sudo docker-compose up -d

# Rebuild 

sudo docker-compose up -d --build

# Rajouter une route 
# nginx

`    location /app1 {
        proxy_pass  http://172.17.0.1:8001/;
    }
`
** rajouter / à la fin de l'url **
