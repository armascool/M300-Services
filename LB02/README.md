
# M300-Services LB02

Das Hauptthema der LB02 ist Docker.

### Vorwissen
Ich habe 0 Vorwissen über Docker.

### Wissenzuwachs
Mir ist bewusst wie ich Docker benutzen kann um Container zu erstellen und zu benutzen.


## Übersicht der LB02

M300 - M300 - 30 Container

* [Github kennengelernt und benutzt (Repository erstellt)](https://github.com/armascool/M300-Services#github-kennengelernt-und-benutzt-repository-erstellt)
* [Git Bash kennengelernt und benutzt (Repository klonen auf meinen PC und Änderungen hochladen](https://github.com/armascool/M300-Services#git-bash-kennengelernt-und-benutzt)
* [Virtualbox heruntergeladen, Ubuntu VM erstellt, updated und synaptic und apache webserver installiert](https://github.com/armascool/M300-Services#virtualbox)
* [Vagrant installiert und damit eine VM ganz einfach erstellt via Vagrant Konsole](https://github.com/armascool/M300-Services/blob/main/README.md#vagrant)
* [Visual Studio Code installiert und alle Abhängigkeiten, welche für Github benötigt werden, installiert](https://github.com/armascool/M300-Services#visual-studio-code)
* [mit Visual Studio Code README file von Github bearbeitet und pushen (das was Sie hier lesen)](https://github.com/armascool/M300-Services#readme-file-einrichten)
* [Netzwerkplan meiner Infrastruktur](https://github.com/armascool/M300-Services/blob/main/README.md#netzwerkplan-meiner-infrastruktur)
* [Markdown Befehle](https://github.com/armascool/M300-Services/blob/main/README.md#markdown-befehle)


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

Achtung exterm cooler Markdown Tabellen erstell Tool!!!!! --> [**!!!!!!!!hier klicken!!!!!!!!**](https://www.tablesgenerator.com/markdown_tables)
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
#### Was ist eine Firewall und was macht sie?
* Firewall dient zur Sicherheit von Geräten und Netzwerken in dem sie den Datenverkehr regelt
* In einer Firewall befinden sich verschiedene NICs, also Netzwerkanschlüsse
* Diese NICs braucht man dann um Regeln zu erstellen, also zB: alles was beim NIC 1 reinkommt und zu NIC2 hin will, wird blockiert.
* Firewalls kann man als physisches Gerät kaufen, diese können günstig bis sehr teuer sein
* das wichtige bei einer Firewall ist aber der Software Aspket, dort regelt man alles, dieser ist natürlich auch bei einer physischen Firewall bereits drauf
* eine Firewall kann auch eine einfache Virtuelle Maschine mit einer gratis Firewall Software darauf installiert sein --> siehe [UFW Firewall](https://wiki.ubuntuusers.de/ufw/)

#### Was ist ein Proxy (auch Forward-Proxy genannt)?
* das ist ein Server, besser gesagt Computer mit einer anderen öffentlichen IP Adresse, über den man im Internet Sachen aufruft
* somit kann man als Benutzer/Client seine Identität schützen und verbergen
* bei einem Proxy kann man einstellen, dass man gewisse Websites sperrt
* man kann gemanagete Firemengeräte so einstellen, dass sie immer über einen Proxy ins Internet müssen und nie direkt
* umformuliert kann man auch sagen  
*"Grundlegende Aufgabe des Proxy-Servers ist es, Client-Anfragen an einen Server stellvertretend entgegenzunehmen und mit der eigenen IP-Adresse an den Zielrechner weiterzuleiten. Bei dieser Art der Kommunikation besteht keine direkte Verbindung zwischen Absender und Empfänger."*
--> [Quelle](https://www.ionos.de/digitalguide/server/knowhow/was-ist-ein-proxy-server/#:~:text=Grundlegende%20Aufgabe%20des%20Proxy%2DServers,Verbindung%20zwischen%20Absender%20und%20Empf%C3%A4nger.)
* Geoblocking kann so umgangen werden


#### Was ist ein Reverse Proxy?
* die ist ein Proxy um Server zu schützen
* dieser macht, dass wenn Clients aus dem Internet auf einen meiner Webserver zugreiffen will, wird die Anfrag erst zum Reverse Proxy geschickt  
hier wird überprüft, ob die Anfrage normal aussieht --> Anhand von konfigurierten Sicherheitsregeln geprüft und wenn alles okay ist  
wird die Anfrage (Website aufrufen) an den Webserver weitergeleitet
* schützt vor DDOS Attacken, kann als Firewall dienen, kann Bots und Hacker blocken anhand von Regeln und auffälligen Serveranfragen
* Bandbreitenkontrolle und Lastenverteilung
* Anonymisierung


## SSH

#### Was ist SSH?
* SSH --> Secure Shell
* Authentifizierung der Gegenstelle, kein Ansprechen falscher Ziele
* Verschlüsselung der Datenübertragung, kein Mithören durch Unbefugte
* Datenintegrität, keine Manipulation der übertragenen Daten
* Fernzugriff von PC über eine Konsole

#### SSH wichtige Befehle
| Command                           | Beschreibung                                          |
|-----------------------------------|-------------------------------------------------------|
| ssh 192.168.56.101   ssh Hostname | verbindung ssh aufbauen entweder mit IP oder Hostname |
| ssh username@hostname_oder_IP     | verbindung ssh aufbauen + Login                       |
| ssh hostname_oder_IP -p 3322      | verbindung ssh aufbauen über anderen Port             |

#### Public Key Verfahren
Man kann mit Hilfe von einem Public Key Verfahren seine SSH Verbindungen noch sicherer machen. Um dies zu ermöglichen wird asymmetrische Verschlüsselung genutzt, um den Benutzer zu authentifizieren.

Die public Keys des Benutzers befindet sich dabei in der Datei ~/.ssh/authorized_keys des Zielsystems, der private Schlüssel in einer Datei (meist id_rsa) im Verzeichnis ~/.ssh auf dem lokalen System, wo er zusätzlich von einer "Pass Phrase" geschützt wird.

Wenn man sich nun mit der Public-Key-Methode auf einem SSH-Server anmelden möchte, so schickt der Server dem Client eine zufällig generierte Challenge. Der Client verschlüsselt diesen Datenblock mit seinem privaten Schlüssel, (wofür nötigenfalls die Passphrase abgefragt wird,) und wenn der Server diesen Chiffre mit dem zugehörigen öffentlichen Schlüssel wieder entschlüsseln kann, ist die Identität des Benutzers bestätigt.


## Authentifizierung & Autorisierung
#### Was ist Authentifizierung?
* Hier wird geprüft, ob die Person, die sich für wen ausgibt, auch diese ist --> besser gesagt username und password wird überprüft


#### Was ist Autorisierung?
* Wenn eine Authentifizierung korrekt durchlief, bekommt der User/Benutzer die Rechte erteilt, welche Ihm zustehen  
das können zum Beispiel schreib- und oder lese Rechte sein




