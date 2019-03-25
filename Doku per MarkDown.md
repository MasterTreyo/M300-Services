# Modul 300

# Einleitung


Diese Dokumentation soll zur Erkenntnis bringen, welche Punkte ich erledigt habe, und wie ich vorgegangen bin. Diese Punkte habe ich anhand der Folien und Anleitungen im BSCW und auf GitHub bearbeitet.

# Kriterien 1 (Umgebung)

## Virtual Box

**Virtualbox installieren:**

1. Zuerst muss die VirtualBox-Anwendung installiert werden. Der Installer lässt sich unter [Virtualbox.org](https://«www.virtualbox.org) herunterladen.
2. Die Installation erfolgt GUI-basiert, jedoch Standard (ohne spezielle Anpassungen). Daher wird an dieser Stelle auf eine Erklärung verzichtet.
3. Sobald der Vorgang abgeschlossen wurde, kann mit dem Herunterladen der ISO-Datei und der VM-Erstellung fortgefahren werden.

## Vagrant

**Vagrant installieren:**

1. Die Anwendung kann unter [Vagrantup.com](https://www.vagrantup.com/) heruntergeladen werden.
2. Die Installation erfolgt, wie alle anderen Anwendungen, GUI-basiert, jedoch Standard (ohne spezielle Anpassungen). Daher wird an dieser Stelle ebenfalls auf eine Erklärung verzichtet.
3. Sobald der Vorgang abgeschlossen wurde, kann mit dem Erstellen einer VM fortgefahren werden.

## Visualstudio-Code

**Visualstudio-Code installieren:**

1. [Hier](https://code.visualstudio.com/download) lässt sich der Installer herunterladen.
2. Auf &quot;Download&quot; klicken und warten, bis das Fenster zum Herunterladen erscheint. Anschliessend den Download des Installers starten
3. Die Installation erfolgt auch hier GUI-basiert. Wiederum aber Standard (ohne spezielle Anpassungen), sodass an dieser Stelle auf eine Erklärung ebenfalls verzichtet wird.
4. Sobald der Vorgang abgeschlossen wurde, kann mit dem Herunterladen der ISO-Datei und der VM-Erstellung fortgefahren werden.

**Extensions installieren:**

- Markdown All in One (von Yu Zhang)
- Vagrant Extension (von Marco Stanzi)
- vscode-pdf Extension (von tomiko1207)
- Visual Studio Code öffnen
- Die Tastenkombination CTRL + SHIFT + X drücken und in der Suchleiste die erwähnten Extensions suchen
- Auf Install klicken und anschliessend auf Reload, um die Extension in den Arbeitsbereich zu laden.
- Nun können die Extensions angewendet werden. Für Markdown ist diese [Liste](https://github.com/adam-p/markdown-here/wiki) sehr hilfreich.

## Git-Client

**Client installieren:**

1. Für die Client-Installation muss der Installer [hier](https://git-scm.com/downloads) heruntergeladen werden
2. Die Installation erfolgt GUI-basiert, jedoch Standard (ohne speziellen Anpassungen). Daher wird an dieser Stelle auf eine Erklärung verzichtet.
3. Sobald der Vorgang abgeschlossen wurde, kann mit der Konfiguration fortgefahren werden.

**Client konfigurieren:**

1. Terminal (_Bash_) öffnen
2. Git konfigurieren mit Informationen des GitHub-Accounts:
3.     $ git config --global user.name "<Saibot_201>";

       $ git config --global user.email "<tobi-alex@gmx.ch>";

4. Konfiguration abgeschlossen

**Repository erstellen:**

1. Anmelden unter [github.com](http://www.github.com/)
2. Innerhalb der Willkommens-Seite auf  **Start a project**  klicken
3. Unter  **Repository name**  einen Name definieren (z.B. M300-Services)
4. Optional: kurze Beschreibung eingeben
5. Radio-Button bei  **Public**  belassen
6. Haken bei  **Initialize this repository with a README**  setzen
7. Auf  **Create repository**  klicken

## SSH-Key für Client erstellt

**SSH-Key erstellen (lokal):**

1. Folgenden Befehl mit der Account-E-Mail von GitHub einfügen:

       $  ssh-keygen -t rsa -b 4096 -C &quot;tobi-alex@gmx.ch&quot;

2. Neuer SSH-Key wird erstellt:

       Generating public/private rsa key pair.

3. Bei der Abfrage, unter welchem Namen der Schlüssel gespeichert werden soll, die Enter-Taste drücken (für Standard):

       Enter a file in which to save the key (~/.ssh/id_rsa): [Press enter]

4. Nun kann ein Passwort für den Key festgelegt werden. Ich empfehle dieses zu setzen und anschliessend dem SSH-Agent zu hinterlegen, sodass keine erneute Eingabe (z.B. beim Pushen) notwendig ist:

       Enter passphrase (empty for no passphrase): [Passwort]
       Enter same passphrase again: [Passwort wiederholen]

**SSH-Key bei GitHub hinzufügen:**

1. Anmelden unter [github.com](http://www.github.com/)
2. Auf Benutzerkonto klicken (oben rechts) und den Punkt  **Settings**  aufrufen
3. Unter den Menübereichen auf der linken Seite zum Abschnitt  **SSH und GPG keys**  wechseln
4. Auf  **New SSH key**  klicken
5. Im Formular unter  **Title**  eine Bezeichnung vergeben (z.B. MB SSH-Key)
6. Den zuvor kopierten Key mit _CTRL + V_ einfügen und auf  **Add SSH key**  klicken
7. Der Schlüssel (SSH-Key) sollte nun in der übergeordneten Liste auftauchen

1. 3.
# Kriterien 2 (PLE)


## GitHub oder Gitlab-Account ist erstellt

Anmelden unter [github.com](http://www.github.com/)
Danach muss man noch das Konto per E-Mail verifizieren.

## Git-Client wurde verwendet

**Repository zum Test klonen:**

1. Zu Testzwecken soll ein Repository geklont werden. Dazu sind folgende Befehle notwendig:
2. Terminal (_Bash_) öffnen
3. Repository klonen:

       $ git clone https://github.com/mc-b/M300

4. In das M300-Verzeichnis wechseln:

       $ cd M300

5. Repository aktualisieren und Status anzeigen:

       $ git pull

       Already up to date.

       $ git status

       Your branch is up to date with 'origin/master'.

6. Die Statusmeldung soll dabei mitteilen, dass das lokale Repository mit dem Originalen übereinstimmt.

# Kriterien 3 (Vagrant)

## Bestehende VM aus Vagrant-Cloud einrichten

[Hier](https://app.vagrantup.com/boxes/search) kann man eine Vagrant Box suchen und auswählen.

**Box hinzufügen**
Hinzufügen einer Box zur lokalen Registry:

      $ vagrant box add [box-name]

In der lokalen Registry vorhandene Boxen anzeigen:

      $ vagrant box list

**VM erstellen**
Vagrantfile Erzeugen und Provisionierung starten:

      $ mkdir myserver

      $ cd myserver

      $ vagrant init ubuntu/xenial64

      $ vagrant up

Aktueller Status der VM anzeigen:

      $ vagrant status

**VM updaten**
Nach Änderungen im Vagrantfile kann ein Server wie folgt aktualisiert werden:

      $ vagrant provision

oder

      $ vagrant destroy -f

      $ vagrant up

**VM löschen**
Die VM kann wie folgt gelöscht werden:

      $ vagrant destroy -f

## Kennt Vagrant-Befehle

| **Befehl** | **Beschreibung** |
| --- | --- |
| vagrant init | Initialisiert im aktuellen Verzeichnis eine Vagrant-Umgebung und erstellt, falls nicht vorhanden, ein Vagrantfile |
| vagrant up | Erzeugt und Konfiguriert eine neue Virtuelle Maschine, basierend auf dem Vagrantfile |
| vagrant ssh | Baut eine SSH-Verbindung zur gewünschten VM auf |
| vagrant status | Zeigt den aktuellen Status der VM an |
| vagrant port | Zeigt die Weitergeleiteten Ports der VM an |
| vagrant halt | Stoppt die laufende Virtuelle Maschine |
| vagrant destroy | Stoppt die Virtuelle Maschine und zerstört sie. |

## Andere, vorgefertigte VM auf eigenem Notebook aufgesetzt

Ich habe bei mir 2 extra Ubuntu VM&#39;s mit Vagrant aufgesetzt, einmal «Trusty» und «Xenial».

Wenn man aus seiner VM eine Vagrant Box machen möchte, kann man der [Anleitung](https://scotch.io/tutorials/how-to-create-a-vagrant-base-box-from-an-existing-one) folgen. Sie kann dann wieder als Backup gebraucht werden, oder man kann sie so weiterzugeben.

# Kriterien 4 (Sicherheitsaspekte)

## Firewall eingerichtet inkl. Rules

**Ausgabe der offenen Ports**

    $ netstat -tulpen

**Installation**

    $ sudo apt-get install ufw

**Start / Stop**

    $ sudo ufw status

    $ sudo ufw enable

    $ sudo ufw disable

**Firewall-Regeln**

    # Port 80 (HTTP) öffnen für alle

    vagrant ssh web

    sudo ufw allow 80/tcp

    exit

    # Port 22 (SSH) nur für den Host (wo die VM laufen) öffnen

    vagrant ssh web

    w

    sudo ufw allow from [Meine-IP] to any port 22

    exit

**Zugriff testen**

    $ curl -f 192.168.55.101

    $ curl -f 192.168.55.100:3306

**Löschen von Regeln**

    $ sudo ufw status numbered

    $ sudo ufw delete 1

## Reverse-Proxy eingerichtet

**Installation**  Dazu müssen folgende Module installiert werden:

    $ sudo apt-get install libapache2-mod-proxy-html

    $ sudo apt-get install libxml2-dev

Anschliessend die Module in Apache aktivieren:

    $ sudo a2enmod proxy

    $ sudo a2enmod proxy\_html

    $ sudo a2enmod proxy\_http

Die Datei /etc/apache2/apache2.conf wie folgt ergänzen:

    ServerName localhost

Apache-Webserver neu starten:

    $ sudo service apache2 restart

## Benutzer- und Rechtevergabe ist eingerichtet

Wenn man sehen möchte, welche Rechte momentan in dem Ordner vergeben sind, gibt man «$ ll» ein.

Die Ausgabe könnte sein: drwxr-xr-x …

Der erste Buchstabe kann «d» oder «-» sein (directory oder file). Danach folgen Zugriffsrechte.

r = read, w = write, x = execute, s = SUID-Bit, S = SGID-Bit, t = Sticky-Bit

Befehle zur Bearbeitung der Rechte:

| **Befehl** | **Funktion** |
| --- | --- |
| chmod | Dient zum Setzen der Dateirechte |
| chown | Dient zum Ändern des Dateibesitzers |
| chgrp | Dient zum Ändern der Gruppe einer Date |



# Kriterien 5 (Zusätzliche Bewertungspunkte)


### Vergleich Vorwissen - Wissenszuwachs

- Vagrant
- GitHub

## Reflexion

Für mich war dieses Modul bis jetzt das Kennenlernen von Vagrant und GitHub. Ich habe war zwar vorher schon oft auf GitHub, ob extra oder weil ich etwas auf GitHub gefunden habe, aber mit GitHub arbeiten konnte ich noch nicht. Ausserdem war ich sehr überrascht, dass man mit Vagrant so einfach VM&#39;s neu aufsetzen kann. Das ist etwas, was ich auch persönlich wahrscheinlich nochmals brauchen werde, damit ich keine VM&#39;s mehr selber aufsetzen muss, sondern einfach herunterladen kann. Von MarkDown bin ich kein Freund geworden, weshalb ich meine Dokumentationen auf jeden Fall weiterhin mit Word machen werde.