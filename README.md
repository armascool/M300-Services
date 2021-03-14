# M300-Services

Das Modul 300 habe ich, Armas Krebs bei Herrn Kälin. Ich bin in der ST18c und bin zur Zeit im 3. Lehrjahr als Systemtechniker EFZ bei der SwissTXT und besuche die Berufsschule TBZ.

## Übersicht der LB01

M300 - 10 Toolumgebung

* [Github kennengelernt und benutzt (Repository erstellt)](https://github.com/armascool/M300-Services#github-kennengelernt-und-benutzt-repository-erstellt)
* [Git Bash kennengelernt und benutzt (Repository klonen auf meinen PC und Änderungen hochladen](https://github.com/armascool/M300-Services#git-bash-kennengelernt-und-benutzt)
* [Virtualbox heruntergeladen, Ubuntu VM erstellt, updated und synaptic und apache webserver installiert](https://github.com/armascool/M300-Services#virtualbox)
* [Vagrant installiert und damit eine VM ganz einfach erstellt via Vagrant Konsole](https://github.com/armascool/M300-Services/blob/main/README.md#vagrant)
* [Visual Studio Code installiert und alle Abhängigkeiten, welche für Github benötigt werden, installiert](https://github.com/armascool/M300-Services#visual-studio-code)
* [mit Visual Studio Code README file von Github bearbeitet und pushen (das was Sie hier lesen)](https://github.com/armascool/M300-Services#readme-file-einrichten)

M300 - 20 Infrastruktur-Automatisierung

* Cloud Computing,SaaS, PaaS, IaaS kennengelernt
* Infrastructure as Code
* Vagrant
* Packer
* AWS Cloud

M300 - 25 Infrastruktur-Sicherheit

* Firewall & Reverse Proxy
* Benutzer- & Rechteverwaltung
* SSH
* Authentifizierung & Autorisierung

## Github kennengelernt und benutzt (Repository erstellt)

Github Account erstellen unter                      --> [Hier klicken](https://github.com/join?ref_cta=Sign+up&ref_loc=header+logged+out&ref_page=%2F&source=header-home)  
Github einloggen, falls Account bereits vorhanden   --> [Hier klicken](https://github.com/login)  
Das erstellen vom Repository habe ich 1 zu 1 nach [dieser Anleitung](https://github.com/mc-b/M300/tree/master/10-Toolumgebung#-01---github-account) gemacht und ich brauche hier nichts mehr hinzuzufügen.

## Git Bash kennengelernt und benutzt

Um mit GitHub zu kommunizieren und die Repositories lokal bearbeiten zu können und sie wieder auf GitHub hochzuladen können, muss man es [hier](https://git-scm.com/downloads) herunterladen.
GitBash habe ich folgendermassen konfiguriert:  
```
$ git config --global user.name "<username>"
$ git config --global user.email "<e-mail>"
$ git clone https://github.com/armascool/M300-Services
$ cd M300
$ git pull
Already up to date.
$ git status
Your branch is up to date with 'origin/master'.
$ cd C:\Users\Armas\M300-Services
$ mkdir MeinLokalesRepository
$ git clone git@github.com:armascool/M300-Services.git
Cloning into 'M300-Services'...
$ git pull
Already up to date.
```
Um das Repository hochzuladen, falls ich eine Änderung lokal an meinem Repository vorgenommen habe, gehe ich wie folgt vor:

```
$ cd Pfad/zu/meinem/Repository
$ git add -A .
$ git commit -m "Mein Kommentar"
$ git push
```
## Virtualbox

Virtualbox, habe ich [hier](https://www.virtualbox.org/) gedownloaded und installiert.  Da mir der Prozess mehr als vertraut ist, kann ich mir die Doku sparen. [Hier](https://github.com/mc-b/M300/tree/master/10-Toolumgebung#--03---virtualbox) ist das Tutorial, falls ich in der Zukunft keinen Plan mehr habe.  
Als Betriebssystem für die VM habe ich folgendes OS verwendet --> Ubuntu Desktop [16.04.05](http://old-releases.ubuntu.com/releases/16.04.5/)  
Folgende Befehle habe ich in der VM abgefeuert:
```
$  sudo apt-get update   #Paketlisten des Paketmanagement-Systems "APT" neu einlesen
$  sudo apt-get upgrade   #Installierte Pakete wenn möglich auf verbesserte Versionen aktualisieren
$  sudo reboot           #System-Neustart durchführen
$  sudo apt-get install synaptic
$  sudo reboot
```
Mit Browser prüfen, ob der Standard-Content des Webservers unter "http://127.0.0.01:80" (localhost) erreichbar ist.

## Vagrant

Vagrant ist eine freie Ruby-Anwendung zur Erstellung und Verwaltung virtueller Maschinen und ermöglicht einfache Softwareverteilung.  
[---Download von Vagrant---](https://www.vagrantup.com/)  

VM erstellen:  
```
 $ cd Wohin/auch/immer
 $ mkdir MeineVagrantVM
 $ cd MeineVagrantVM
 $ vagrant init ubuntu/xenial64        #Vagrantfile erzeugen
 $ vagrant up --provider virtualbox    #Virtuelle Maschine erstellen & starten
 $ cd Pfad/zu/meiner/Vagrant-VM      #Zum Verzeichnis der VM wechseln
 $ vagrant ssh                       #SSH-Verbindung zur VM aufbauen
 #Anschliessend können ganz normale Bash-Befehle abgesetzt werden:
 $ ls -l /bin  #Bin-Verzeichnis anzeigen
 $ df -h       #Freier Festplattenspeicher
 $ free -m     #Freier Arbeitsspeicher
```

## Visual Studio Code

Dieser freie Quelltext-Editor von Microsoft, ermöglicht uns, unsere Workflows besser zu gestalten und damit die Arbeit um einiges leichter zu machen.  
[---Download von VSC---](https://code.visualstudio.com/)  

Folgende extensions brauche ich, damit die Integration mit Github funktioniert:  
1. Markdown All in One (von Yu Zhang)
2. Vagrant Extension (von Marco Stanzi)
3. vscode-pdf Extension (von tomiko1207)  
um diese zu installieren --> CTRL + SHIFT + X  

[Einstellungen anpassen von VSC](https://github.com/mc-b/M300/tree/master/10-Toolumgebung#einstellungen-anpassen), da ansonsten die Files der VMs ins Cloud-Repository hochgeladen werden.

## README file einrichten
1.
2.
1. Visual Studio Code öffnen
2. Änderungen an entsprechenden Dateien des lokalen Repositorys vornehmen
3. In der linken Leiste das Symbol mit einer "1" aufrufen
4. Unter dem Abschnitt Changes die betroffenen Files bezüglich ihres Changes "stagen" (Stage Changes)
5. Nachricht hinterlegen (Message) und Haken (Commit) setzen
6. Bei den 3 Punkten (...) die Funktion Push aufrufen
7. Warten, bis Dateien vollständig gepusht wurden


#        
