![Texto alternativo](https://github.com/dart-security/metasploit-compose/blob/master/doc.png)

[![Channel](https://img.shields.io/badge/channel-YouTube-red)](https://www.youtube.com/channel/UCiuZK5geN3OCGeBxuXMfHEQ)

[![Docker](https://img.shields.io/badge/Docker-19.03.8-blue)](https://www.docker.com/)
[![Metasploit](https://img.shields.io/badge/metasploit-latest-success)](https://hub.docker.com/_/owncloud)
[![postgresql](https://img.shields.io/badge/postgresql-latest-blue)](https://hub.docker.com/_/mysql)

## Uso
Clonar el respositorio en tu maquina con docker instaladoy docker-compose:
```bash
➜ git clone https://github.com/dart-security/metasploit-compose
```
si no tienes docker-compose instalado puedes instalarlo con pip:
```bash
➜ pip3 install docker-compose
```
Despues de tener docker-compose ahora en nuestro "home" va a crear uns carpeta .msf4 en la cual metasploit gurdara los datos
```bash
➜ mkdir .msf4
➜ sudo chown 1000 .msf4
```
## Ejecutando
Para ejecutar el compose usaremos la siguiente liunea:
```bash
➜ docker-compose up -d
```
si requerimos de admin añadimos sudo:
```bash
➜ sudo docker-compose up -d
```
con docker-compose ps verificamos los contenedores
```bash
➜  metasploit docker-compose ps
   Name                 Command               State           Ports         
----------------------------------------------------------------------------
metasploit   docker/entrypoint.sh ./msf ...   Up      0.0.0.0:4444->4444/tcp
postgres     docker-entrypoint.sh postgres    Up      0.0.0.0:5432->5432/tcp
```
## Ingresando al contenedor
Para ingresar al contenedor tenemos que ejecutar:
```bash
docker xec -ti metsaploit docker/entrypoint.sh ./msfconsole -r docker/msfconsole.rc -y $APP_HOME/config/database.yml
```
![Texto alternativo](https://github.com/dart-security/metasploit-compose/blob/master/msf4.png)
