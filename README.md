Installationsanleitung Raspberry Pi 4+

 1. Download Raspberry OS Image
 2. Create empty SSH file in root of SD card
	  sudo apt-get update
	  sudo apt-get upgrade -y

 1. sudo apt install curl
 2. sudo curl -fsSL https://get.docker.com -o get-docker.sh
 3. sudo sh get-docker.sh
 4. sudo apt install python-pip -y
 5. sudo pip install docker-compose
 6. sudo apt install git -y
 7. sudo git clone https://github.com/nothingkix/docker
 8. sudo rm get-docker.sh

 6. sudo docker pull portainer/portainer
 7. sudo docker run -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock --restart always --name portainer portainer/portainer -H unix:///var/run/docker.sock
 
 Aufruf über Webbrowser: http://raspberry.local:9000


# Docker Container

Dieses Repository ist eine Sammlung von Docker-Compose Dateien. 

## Aufbau
Jedes Verzeichnis enthält nur eine Software. Es lassen sich natürlich auch mehrere Produkte miteinander kombinieren um so die Anzahl an docker-compose.yaml Dateien zu verringern. Sollte eine Software eine Datenbank oder ähnliches benötigten, ist diese natürlich in der entsprechenden compose Datei enthalten.

Ich verwende Traefik als Reverse Proxy. Daher sind alle Softwareprodukte schon mit den entsprechenden Labels für Traefik ausgestattet. Diese müssen nur nach bedarf angepasst werden.

Es werden keine Docker Volumes verwendet sondern bind mounts! Als Standardverzeichnis wird bei mir ````/var/docker```` genutzt. Sollte das für dich kein gangbarer Weg sein, musst du auch hier die Dateien anpassen.

# Wichtiges
Im Laufe der Zeit können sich Produkte ändern oder nicht mehr durch die Entwickler gewartet werden. Bitte habt Verständnis dafür, dass dieses Repository nicht vollständig und zu jeder Zeit korrekt sein kann. Außerdem sind vor Benutzung immer die Dummy-Passwörter durch komplexe eigene Passwörter zu ersetzen!

# Software
Alphabetisch sortiert

## B
* Bitwarden_rs (https://github.com/dani-garcia/bitwarden_rs)

## C
* Cloudflare-ddns


## I
* influxdb (https://www.influxdata.com/products/influxdb/)

## M
* Monitoring (Node Exporter, Prometheus, cAdvisor, Grafana)

## N
* Nextcloud (https://nextcloud.com)
* NTP Server

## P
* Pi-hole (https://pi-hole.net)
* Portainer (https://www.portainer.io)

## T
* Traefik (https://traefik.io)
