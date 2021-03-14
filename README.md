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
```
Give an example
```

## Vagrant

Explain what these tests test and why

```
Give an example
```

## Visual Studio Code

Add additional notes about how to deploy this on a live system

## README file einrichten

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds
