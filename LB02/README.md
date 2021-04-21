
# M300-Services LB02

Das Hauptthema der LB02 ist die Containerisierung mit den Programmen Docker und Kubernetes.

### Vorwissen
Ich habe vor der LB02 keinerlei Vorkenntnisse über Docker und Kubernetes gehabt.

### Wissenzuwachs
Ich habe gelernt wie man mit Dockerfiles, Docker Images erstellt und wie man mit Docker Images Container erstellt und diese verwendet. Ich habe grundlegende Commands von Docker gelernt. Ich habe auch gelernt wie man einen Apache Webserver, der von ausserhalb dem Container erreichbar ist, erstellt. Danach habe ich mir angeschaut und ausgetestet wie Dockerhub funktioniert.
Als nächstes habe ich mir die Sicherheit unter Docker unter die Lupe genommen und gelernt, dass ...


## Übersicht der LB02

M300 - 30 Container

* [Was sind Container?](https://github.com/armascool/M300-Services/blob/main/LB02/README.md#was-sind-container)
* [Was ist Docker?](https://github.com/armascool/M300-Services/blob/main/LB02/README.md#was-ist-docker)
* [Docker Befehle](https://github.com/armascool/M300-Services/blob/main/LB02/README.md#docker-befehle)
* [Docker File Befehle](https://github.com/armascool/M300-Services/blob/main/LB02/README.md#docker-file-befehle)
* [Docker Tutorial](https://github.com/armascool/M300-Services/blob/main/LB02/README.md#docker-tutorial)
* [Docker Volumes](https://github.com/armascool/M300-Services/blob/main/LB02/README.md#docker-volumes)
* [Image-Bereitstellung](https://github.com/armascool/M300-Services/blob/main/LB02/README.md#image-bereitstellung)
* [Netzwerkplan meiner Infrastruktur](https://github.com/armascool/M300-Services/blob/main/LB02/README.md#netzwerkplan-meiner-infrastruktur)

M300 - 35 Sicherheit

* [Sicherheiten](https://github.com/armascool/M300-Services/blob/main/LB02/README.md#sicherheiten)

M300 - 40 Kubernetes
* [Was ist Kubernetes?](https://github.com/armascool/M300-Services/blob/main/LB02/README.md#was-ist-kubernetes)
* [Kubernetes Befehle](https://github.com/armascool/M300-Services/blob/main/LB02/README.md#kubernetes-befehle)
* [Kubernetes](https://github.com/armascool/M300-Services/blob/main/LB02/README.md#kubernetes)
* [Service](https://github.com/armascool/M300-Services/blob/main/LB02/README.md#service)

## Was sind Container?
Container gibt es in der IT, weil es eine Problematik gib wenn man eine Software austesten möchte. Das Problem ist, dass jedes Programm abhängig ist von gewissen Sachen ihrer Umgebung. Diese Sachen sind Libraries und Systemeinstellungen. Mit Umgebung ist das gemeint, wo die Software getestet wird, also in einer Test oder Produktiven Umgebung. Eine weitere Problematik ist das Betriebsystem auf dem die getestete Software läuft, die Version vom OS und die Einstellungen, Netzwerk Einstellungen. 

Jetzt kommen diese Container zum Zuge. Dank Containern kann man die "optimale" Umgebung für einen Softwaretest mobil und flexibel und einfach erstellen, von System zu System verschieben ohne Probleme. Das macht die sogenannte Abschottung des Containers möglich. Es ist etwa gleich wie bei einer virtuellen Maschine. Es ist so abgeschottet, sodass man es leicht erstellen, zerstören, starten und verschieben kann ohne Probleme bei einer anderen Umgebung oder so zu bekommen.

Das Problem mit VMs sind dass jeder Software Test eine eigene VM benötigt. Jede einzelne VM benötigt ein eigenes Betriebsystem, dies läuft auf dem virtualisierendem Betriebsystem. Das lässt also nicht so viele Testumgebungen gleichzeitig zur Verfügung wie Container Lösungen. Das kommt daher, das Container kein eigenes Betriebsystem benötigen, sonder auf dem Host Betriebsystem laufen, aber die für die Testumgebung benötige Software, Ihre Libraries und Einstellungen sind aber alles in einem Container abgeschottet von der Host Betriebsystem. Ausserdem können Container sehr viel schneller erstellt, zerstört, gestartet, gestoppt und leichter verschoben werden. VM fressen einem also die Ressourcen weg Container aber nicht so sehr, diese benötigen viel weniger weil das Gast Betriebsystem weg fällt. 
![image](https://user-images.githubusercontent.com/78543196/115438399-a3202700-a20d-11eb-926b-c137a89a7249.png)

## Was ist Docker?
![image](https://user-images.githubusercontent.com/78543196/115438691-fc885600-a20d-11eb-8d73-af94b01e8e36.png)
Die Beschreibung von Wikipedia hat mir ausnahmsweise sehr gefallen.   
"Docker ist eine Freie Software zur Isolierung von Anwendungen mit Hilfe von Containervirtualisierung. Docker vereinfacht die Bereitstellung von Anwendungen, weil sich Container, die alle nötigen Pakete enthalten, leicht als Dateien transportieren und installieren lassen."  

**Docker File:** beschreibt den Inhalt eines Images, und es ist somit die Bauanleitung für Container. Mit build command kann man dann mit dem File ein Image erstellen. 
  
**Docker Image:** Ein Image ist eine Vorlage, also sozusagen ein Bauplan um Docker Container zu erstellen.   
  
**Docker Container:** Ein Container ist eine Umgebung, welche mit auf der Basis von einem Image läuft. Man kann ein Container ganz leicht erstellen, starten, stoppen, löschen und verschieben.
## Docker Befehle
Befehl | Erklärung 
------------ | ------------- | 
`docker run` | Container starten 
`docker ps` |Infos über Container Name, ID, Status 
`docker images` | Listet lokale images auf
`docker rm` | Container löschen
`docker rmi` | Image löschen
`docker start` | Startet gestoppte Container
`docker stop` | Stopt Container
`docker kill` | Stopt Ccontainer sofort
`docker logs`| Container Logs
`docker inspect` | umfangreiche Informationen zu Container
`docker diff` | Zeigt Änderungen auf am Dateisystem des Containers im Verleich zum Image, mit dem er gestartet wurde
`docker top` | Gibt Informationen zu laufenden Prozessen in einem Container aus
`docker build` | Container erstellen mit Hilfe von Bauplan --> Docker File

## Docker File Befehle
Anweisung | Erklärung 
------------ | ------------- | 
`FROM` | Base Image auswahl
`ADD` | kopiert Datei Build Context oder Link in Image
`CMD` | Befehle in dem Container, welche ausgeführt werden sollen
`COPY` | Kopiert Dateien aus dem Build Context in das Image
`ENTRYPOINT` | erstellt eine ausführbare Datei für Start vom Container
`ENV` | Umgebungsvariablen erstellen für Image
`HEASLTCHECK` | Docker prüft den Status der Anwendungen in einem Conatainer
`MAINTAINER` | "Autor-Metadaten" des Image setzen
`RUN` | Führt die angegebenen Anweisungen im Container aus und bestätigt das Ergebnis
`SHELL` | Erlaubt der Shell für folgenden RUN-command zu setzen.
`USER` | Setzt User, welcher in folgeden RUN-, CMD- oder ENTRYPOINT-Anweisungen genutzt werden soll.
`VOLUME` | Deklariert die angegebene Datei oder das Verzeichnis als Volumen
`WORKDIR` | Setzt Arbeitsverzeichnis für alle folgende RUN-, CMD-, ENTRYPOINT-, ADD oder COPY-Anweisung
## Docker Tutorial
Ich habe mit Docker eien Apache Webserver Container erstellt, welcher mit Hilfe vom Port 8080 es meinem Laptop ermöglich den Apache Webserver von meinem Laptop Browser zu erreichen, wenn ich im Wireguard in Herr Kälins Netzwerk verbunden bin.  
  

Als erstes habe ich das Image dazu erstellt.  
```
FROM ubuntu:14.04
MAINTAINER Marcel mc-b Bernet <marcel.bernet@ch-open.ch>

RUN apt-get update
RUN apt-get -q -y install apache2

# Konfiguration Apache
ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2

RUN mkdir -p /var/lock/apache2 /var/run/apache2

EXPOSE 80

VOLUME /var/www/html

CMD /bin/bash -c "source /etc/apache2/envvars && exec /usr/sbin/apache2 -DFOREGROUND"
```

Dann habe ich mit dem Dockerfile ein Docker Image erstellt
`docker build pathvomdockerfile` --> Docker Image ID aufschreiben/ merken

Danach habe ich das Image gestartet
`docker run --rm -d -p 8080:80 -v /web:/var/www/html --name TollerContainer123 ImageID`

Ich habe noch ein kleines HTML Index File gemacht, um den Apache Server zu testen
```
<!DOCTYPE html>
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
<title>M300</title>
</head>
<body>
<h1>LB02 GitHub Repository</h1>
<a>Das GitHub Repository für die LB02 ist unter folgendem Link erreichbar:</a>
<a href="https://github.com/armascool/M300-Services/tree/main/LB02">link to lb02 krebs</a>
</body>
</html>
```
![image](https://user-images.githubusercontent.com/78543196/115452145-598c0800-a21e-11eb-849e-a4d7107d6baf.png)  

auf Container verbinden mit:
```
docker exec -it container_con /bin/bash
```
Dann noch diese Index Datei in den Container kopieren
`docker cp /SpeicherortDerDatei/index.html ContainereName:/var/www/html/`
## Docker Volumes
## Image-Bereitstellung
Hier habe ich einen einfachen Ubuntu Container erstellt und diesen auf Dockerhub gepusht, sodass ihn jetzt jeder auf der Welt benutzen könnte, wenn er wolle.  
  
Dazu musste ich erst einen Container erstellen, dann mich mit docker login auf dockerhub einloggen also in der Konsole einloggen und als letztes noch das Image auf Dockerhub pushen und einmal pullen.
```
docker run -d -t --name dockerhubtest ubuntu    
docker images  
docker ps    
docker exec -it dockerhubtest /bin/bash  
docker login  
docker commit dockerhubtest  armascool/dockerhubtest:v0.1  
docker pull armascool/dockerhubtest:v0.1
```

![image](https://user-images.githubusercontent.com/78543196/115456728-c81f9480-a223-11eb-9af1-5c58ee13140c.png)
![image](https://user-images.githubusercontent.com/78543196/115457338-b12d7200-a224-11eb-891e-423437ca5545.png)

## Netzwerkplan meiner Infrastruktur
![image](https://user-images.githubusercontent.com/78543196/115443557-b46c3200-a213-11eb-9396-ece702c3d4d8.png)


## Sicherheiten
Es gibt verschiedene Methoden Sicherheitsmassnahmen einzuführen. Ich habe folgende ausgetestet.

### non root as standarduser
Das heisst, dass man beim Dockerfile folgendes hineinschreiben muss, sodass man sich beim Docker nicht mit dem root einloggt, sondern einen neuen User erstellt.

```
RUN useradd -ms /bin/bash [username] \
USER [username] \
WORKDIR /home/[username]
```

### read only
Beim Containerstart kann man eine Read-Only option beifügen, um das Dateisystem vor Änderungen zu schützen.
```
docker run --read-only -d -t --name [NameDesContainer] [Image]
```
### Dockerfiles von andereren kopieren birgt Gefahr
Das kommt daher, dass Dockerfiles mit Malware verseucht sein können, dies ist nicht der Fall wenn man sie selber macht.

### Monitoring unter Docker
Das geht zum Beispiel mit dem gratis Monitoring Tool Cadvisior von Google.  
Container erstellen mit cadvisor:  
```
docker run -d --name cadvisor -v /:/rootfs:ro -v /var/run:/var/run:rw -v /sys:/sys:ro -v /var/lib/docker/:/var/lib/docker:ro -p 8010:8080 google/cadvisor:latest
```
Zugriff auf Cadvisor:  
![image](https://user-images.githubusercontent.com/78543196/115520252-41ea6900-a28a-11eb-881b-c01e3b66dd92.png)

## Was ist Kubernetes?
## Kubernetes Befehle
## Kubernetes
## Service
