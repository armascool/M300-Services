# M300-Services

Das Modul 300 habe ich, Armas Krebs bei Herrn Kälin. Ich bin in der ST18c und bin zur Zeit im 3. Lehrjahr als Systemtechniker EFZ bei der SwissTXT und besuche die Berufsschule TBZ.

### Vorwissen
Ich hatte keine Ahnung von den Sachen gehabt, die wir bei diesem Modul angeschaut haben, ausser das erstellen der VM.

### Wissenzuwachs
Ich hoffe, dass mir das Wissen, welches ich unten dokumentiert habe, mir noch für ein Weilchen bleibt.


## Übersicht der LB01

M300 - 10 Toolumgebung

* [Github kennengelernt und benutzt (Repository erstellt)](https://github.com/armascool/M300-Services#github-kennengelernt-und-benutzt-repository-erstellt)
* [Git Bash kennengelernt und benutzt (Repository klonen auf meinen PC und Änderungen hochladen](https://github.com/armascool/M300-Services#git-bash-kennengelernt-und-benutzt)
* [Virtualbox heruntergeladen, Ubuntu VM erstellt, updated und synaptic und apache webserver installiert](https://github.com/armascool/M300-Services#virtualbox)
* [Vagrant installiert und damit eine VM ganz einfach erstellt via Vagrant Konsole](https://github.com/armascool/M300-Services/blob/main/README.md#vagrant)
* [Visual Studio Code installiert und alle Abhängigkeiten, welche für Github benötigt werden, installiert](https://github.com/armascool/M300-Services#visual-studio-code)
* [mit Visual Studio Code README file von Github bearbeitet und pushen (das was Sie hier lesen)](https://github.com/armascool/M300-Services#readme-file-einrichten)
* [Netzwerkplan meiner Infrastruktur](https://github.com/armascool/M300-Services/blob/main/README.md#netzwerkplan-meiner-infrastruktur)
* [Markdown Befehle](https://github.com/armascool/M300-Services/blob/main/README.md#markdown-befehle)

M300 - 20 Infrastruktur-Automatisierung

* [Cloud Computing,SaaS, PaaS, IaaS kennengelernt](https://github.com/armascool/M300-Services/blob/main/README.md#cloud-computingsaas-paas-iaas-kennengelernt)
* [Infrastructure as Code](https://github.com/armascool/M300-Services/blob/main/README.md#infrastructure-as-code)

M300 - 25 Infrastruktur-Sicherheit

* [Firewall & Reverse Proxy](https://github.com/armascool/M300-Services/blob/main/README.md#firewall--reverse-proxy)
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
#### Vagrant Befehlesübersicht

Befehl | Erklärung | Beispiel
------------ | ------------- | -------------
`vagrant init` | Initalisiert im aktuellen Verzeichnis eine Vagrant Umgebung und falls noch kein Vagrant File vorhanden ist erstellt es dieses | `vagrant init ubuntu/xenial64`
`vagrant up` | Fährt diese VM hoch, in welchem Verzeichnis man das ausführt | `vagrant up --provider virtualbox` --> oder nur vagrant up
`vagrant ssh` | Baut eine SSH Verbindung mit dem VM auf | -
`vagrant status` | Zeigt den Status der VM an| -
`vagrant port` | Zeigt Port von PortForwarding an | -
`vagrant halt` | Stoppt VM | -
`vagrant destroy` | Löscht VM | -
`vagrant -v` | Zeigt Vagrant Version an | -

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
1. Visual Studio Code öffnen
2. Änderungen an entsprechenden Dateien des lokalen Repositorys vornehmen
3. In der linken Leiste das Symbol mit einer "1" aufrufen
4. Unter dem Abschnitt Changes die betroffenen Files bezüglich ihres Changes "stagen" (Stage Changes)
5. Nachricht hinterlegen (Message) und Haken (Commit) setzen
6. Bei den 3 Punkten (...) die Funktion Push aufrufen
7. Warten, bis Dateien vollständig gepusht wurden

## Netzwerkplan meiner Infrastruktur
![Netzwerk-Plan-LB01](https://user-images.githubusercontent.com/78543196/111078012-d3302800-84f3-11eb-86bd-d334b63acb16.jpg)



## Markdown Befehle
In diese Modul habe ich gelernt, wie man mit Markdown in GitHub ganz einfach tolle Dokumentationen über ein Repository/Projekt machen kann. Man erstellt ganz einfach ein Markdown file und schreibt und rein was man in dem File haben will. Danach kann man sich eine coole Doku aus dem Internet heraus suchen über Markdown GitHub. Dort gibt es so tolle Befehle wie z.b. # mit dem man einfach eine Überschrift machen kann. 
Man kann auch ganz normale links machen, auf die man klicken kann. Man kann aber auch links machen bei denen nicht der Link im klickbaren Link steht sondern etwas etwas anderes wie z.b. Klick mich oder der Name von einem Programm.  
  
Das Tutorial, das mir am meisten gebracht hat, ist dieses --> [guides.github.com Markdown Tutorial](https://guides.github.com/features/mastering-markdown/)  

#
#
#
## Cloud Computing,SaaS, PaaS, IaaS kennengelernt


Cloud Computing ist die Bereitstellung von IT-Ressourcen durch einen Provider via Internet.   
Als Ressourcen können folgende Beispiele bereitgestellt werden --> 
* Hardware
* Applikationen
* E-Mail
![2](https://user-images.githubusercontent.com/78543196/111645894-75f0eb00-8801-11eb-8543-fa5374eeab89.PNG)  
Bei Cloud Computing, um die Materie zu vereinfachen und um alles besser einorden zu können, gibt es verschiedene Kategorien:

#### Infrastructure as a Service (IaaS)
* Infrastruktur, also Server mit Backupsystem wird bereitgestellt
* On-demand Ressourcen kaufen anstatt physische beschaffung
* gleiche Möglichkeiten wie bei einem normalen Datacenter aber ohne etwas selber physisch zu kaufen und zu betreiben
* flexibelste Cloud Modell und Kunde hat Kontrolle über die ganze Infrastruktur, die er gekauft/gemietet hat
* Beispiele: DigitalOcean, Linode, Rackspace, Amazon Web Services (AWS), Cisco Metapod, Microsoft Azure, Google Compute Engine (GCE)


#### Platform as a Service (PaaS)
* gemacht für Entwickler von Webanwendungen
* Kunde kriegt Plattform zur Verfügung gestellt, diese ist meistens eine VM mit einem Betriebsystem drauf.
* Man kann als Kunde frei entscheiden, was man mit der Plattform macht.
* Verfügbar über Webbrowser oder kleine Anwendungen zum Verbindungsaufbau zur Plattform.
* Beispiele: AWS Elastic Beanstalk, Windows Azure, Heroku, Force.com, Google App Engine, Apache Stratos, OpenShift


#### Software-as-a-Service (SaaS)
* Software, welche über das Internet bereitgestellt wird.
* keine Software muss lokal installiert werden, da sie auf der Cloud läuft.
* günstig, weil mehrere Benutzer gleichzeit Software verwenden können
* meiste über Webbrowser erreichbar
* Beispiele: Google Drive, Gmail, Office 365


## Infrastructure as Code
automatiseren zur schnellen und unkomplizierten Erstellung einer Infrastruktur  
3 verschiedene Anwendungsmöglichkeiten von IaC:
* infrastructure provisioning --> Server, VM erstellen, Netzwerkkonfiguration, loadbalancers (nur Infrastruktur)
* configuration of provisioned infrastructure --> Applikationen installieren und die managen 
* Deployment of application --> Applikation laufen lassen (Zweck von dieser Infrastruktur zum laufen zu bringen)
#
#
#
## Firewall & Reverse Proxy
te

## Benutzer- & Rechteverwaltung
jlkj

## SSH
kjlj

## Authentifizierung & Autorisierung
jkljk

