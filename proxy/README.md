# Setup

sudo docker-compose up -d

# Rebuild 

sudo docker-compose up -d --build

# Rajouter une route sur nginx.conf
# nginx

`    location /app1 {
        proxy_pass  http://172.17.0.1:8001/;
    }
`
</br>
</br>

**rajouter / à la fin de l'url**
# traefik

Il faut qu'il soit dans le même réseau et rajouter les labels

# Angular 

- modifier index.html
- e.g: si on veut que la route soit sur /app1
- au niveau des href de html: rajouter le '/' (pour qu'il prenne en compte le port)

`<base href='/'>` par `<base href='/app1/'>`

# Debug

- Si cela ne fonctionne pas, désactiver le pare feu: sudo ufw disable
