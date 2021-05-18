# Práctica 17

## Balanceo de carga con HAProxy

Para esta práctica se usan los mismos archivos que la práctica anterior pero modificando el docker-compose.yml para añadir HAProxy:

```
lb:
    image: dockercloud/haproxy
    ports:
      - 80:80
      - 1936:1936
    networks:
      - frontend-network
    links:
      - apache
    volumes: 
      - /var/run/docker.sock:/var/run/docker.sock
```

Lo creamos en el puerto 1936. Para acceder desde el navegador necesitamos las credenciales, las cuales se encuentran en el archivo haproxy.cfg dentro del contenedor:

![haproxy.cfg](https://raw.githubusercontent.com/arr588/iaw-practica-17/main/img/1.png)