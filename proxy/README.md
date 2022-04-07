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
- au niveau des href de html: **rajouter le '/' à la fin de l'url (pour qu'il prenne en compte le port)**

`<base href='/'>` par `<base href='/app1/'>`

- Rafraîchir les pages : modifier app-routing.module.ts
```
import { NgModule } from '@angular/core';
...
const routes: Routes = [//routes in here];
@NgModule({
  imports: [
    BrowserModule,
    FormsModule,
    RouterModule.forRoot(routes, { useHash: true })
  ],
  bootstrap: [AppComponent]
})
export class AppModule { }

```

# Debug

- Si cela ne fonctionne pas, désactiver le pare feu: sudo ufw disable
