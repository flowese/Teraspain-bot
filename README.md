# teraspain-bot

![](https://github.com/flowese/teraspain-bot/blob/master/img/tsp_logo.png?raw=true)

![](https://img.shields.io/github/stars/pandao/editor.md.svg) ![](https://img.shields.io/github/forks/pandao/editor.md.svg) ![](https://img.shields.io/github/tag/pandao/editor.md.svg) ![](https://img.shields.io/github/release/pandao/editor.md.svg)

# TERASPAIN ADMIN TOOLS

**Bot personalizable de telegram escrito en bash.**

###  Características

- Bot simple y perfecto para automatizar tareas en entornos linux.
- Admite comandos personalizados.
- Testeado y 100% funcional en debian.
- Integración con comandos rcon para juegos de steam.
- Integración con Plex Media Scanner.
- Permite en envío de mensajes desde el bot a un canal o usuario.
- Proyecto nuevo y en desarrollo.



### Requisitos de funcionamiento
- GNU bash : Testado en bash, version 4.3.30(1)-release.
- curl : Para las gestión de llamadas.
- mcrcon : Para las funciones de rcon.
- zip : Para la gestión de ficheros y funciones de backup.
- telegram : Necesario generar un bot y un token.
- git : Para la instalación y actualización del bot.

### Instalación básica

- Descargarse el repositorio con git y acceder al directorio. 

        git clone https://github.com/flowese/teraspain-bot.git
		cd teraspain-bot/
		nano tsbot.sh
- Editar fichero  tsbot.sh e introducir el token de telegam. 

		TELEGRAMTOKEN="AQUI VA EL TOKEN DE TELEGRAM";

- En el mismo fichero deben editarse las rutas y los comandos deseados.

		# Para añadir nuevos comandos debes usar esta sintaxis exacta: ["/micomando"] = '<comando del sistema>'
		# Por favor, no te olvides de eliminar todos los comandos de ejemplo!
		
		declare -A botcommands
		botcommands=(
		
		##Comandos de interacción.
		
		["/hola"]='echo "Hola @FIRSTNAME, soy el bot oficial de TERASPAIN, estoy aquñi para ayudarte."'
		["/adios"]='echo "Adiós @FIRSTNAME, un placer conocerte, que tengas un buen día :D"'
		["/team"]='echo Master Admins:; echo "@flowese"; echo "@blind"'
		
		##Comandos de Inicio y Ayuda.	
		
		["/start"]="./scripts/helpmenu.sh"
		["/ayuda"]="./scripts/helpmenu.sh"
		["/help"]="./scripts/helpmenu.sh"
		
		##Comandos de Sistema. 	
		
		["/uptime"]="uptime -p"
		["/ping (.*)"]="ping -c 1 -t 1 -W 1 @R1"
		["/pingc"]="./scripts/globalping.sh"
		["/whois ([a-zA-Z0-9\.\-]+)"]="/usr/bin/whois @R1" 	
		["/short (.*)"]="./scripts/short.sh -s @R1"
		["/getip"]="./scripts/gethostip.sh"
		["/rebootds"]="./scripts/rebootsv.sh"
		
		##Comandos de Plex. 
		
		["/plex ([a-zA-Z0-9\.\-]+)"]="service plexmediaserver @R1"
		["/plexscan"]="./scripts/pmsc.sh"
		
		##Comandos de ARK:TSP.
		
		["/synctime"]="./scripts/set_sync_es.sh"
		["/setday"]="./scripts/set_time_day.sh"
		["/setnight"]="./scripts/set_time_night.sh"
		["/players"]="./scripts/listplayers.sh"
		["/getchat"]="./scripts/getchat.sh"
		["/getlog"]="./scripts/getgamelog.sh"	
		["/saveworld"]="./scripts/saveworld.sh"
		["/vermods"]="./scripts/vermods.sh"
		["/updatemods"]="./scripts/update.sh"
		["/backup"]="./scripts/backup.sh"
		["/version"]="./scripts/version.sh"
		["/rcon ([a-zA-Z0-9\.\-]+)"]="mcrcon -s -c -H xxx.xxx.xxx.xxx -P xxxx -p XXXXXX @R1"
		
		)


### Información ampliada

- En el directorio de /scripts se encuentran las funciones.
- Pueden añadirse y/o desactivase comandos segun se prefiera.
- Los comandos o scripts utilizados son desarrollos internos para teraspain.
- Es una primera versión estable y funcional.
- A medida que vayamos puliendo errores y añadiendo funciones las publicaremos.
- Recuerda que este bot lo utilizamos internamente y lo publicamos por si puede ser de utilidad para alguien mas.
- Si gestionas servidores dedicados en linux es de gran utilidad.


### Flujo de solicitudes

- Comunicación cliente/servidor

![](https://github.com/flowese/teraspain-bot/blob/master/img/tsp_logo.png?raw=true)

<h4> Este documento se encuentra en edición </h4>
