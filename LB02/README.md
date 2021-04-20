
# M300-Services LB02

Das Hauptthema der LB02 ist die Containerisierung mit den Programmen Docker und Kubernetes.

### Vorwissen
Ich habe vor der LB02 keinerlei Vorkenntnisse über Docker und Kubernetes gehabt.

### Wissenzuwachs
Unten habe ich dokumentiert, wie ich vorgegangen bin um den Umgang mit Docker und Kubernetes kennenzulernen und was man mit den beiden für Möglichkeiten hat.


## Übersicht der LB02

M300 - 30 Container

* [Was sind Container?](https://github.com/armascool/M300-Services/blob/main/LB02/README.md#was-sind-container)
* [Was ist Docker?](https://github.com/armascool/M300-Services/blob/main/LB02/README.md#was-ist-docker)
* [Docker Befehle](https://github.com/armascool/M300-Services/blob/main/LB02/README.md#docker-befehle)
* [Docker Tutorial](https://github.com/armascool/M300-Services/blob/main/LB02/README.md#docker-tutorial)
* [Docker Volumes](https://github.com/armascool/M300-Services/blob/main/LB02/README.md#docker-volumes)
* [Image-Bereitstellung](https://github.com/armascool/M300-Services/blob/main/LB02/README.md#image-bereitstellung)
* [Netzwerkplan meiner Infrastruktur](https://github.com/armascool/M300-Services/blob/main/LB02/README.md#netzwerkplan-meiner-infrastruktur)


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
## Docker Tutorial
## Docker Volumes
## Image-Bereitstellung
## Netzwerkplan meiner Infrastruktur

