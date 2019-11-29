# linuxmuster-mrbs

MRBS Docker App für linuxmuster. 

TESTVERSION - **NICHT PRODUKTIV VERWENDEN**

## Verwendung

Entweder du hast schin einen Dockerhost mit docker, docker-compose, dehydrated und nginx oder du erzeugst dirkurz einen Dockerhost mit create-docker-host: https://github.com/linuxmuster-ext-docker/create-docker-host

### Dienstenamen und Zertifikat

Zuerst musst du dir Dienstenamen ausdenken und SSL-Zertifikat besorgen. Also z.B. mrbs.meine-schule.tld

* Lege einen DNS Eintrag für deine Dockerapp, z.B. mrbs.meine-schule.tld, der auf die IP des Dockerhosts zeigt. Das darf auch ein CNAME sein.
* Trage diesen Host in die Datei ``/etc/dehydrated/domains.txt`` ein.
* Führe den Befehl ``dehydrated -c`` aus. Jetzt hast du die Zertifikate im Verzeichnis /var/lib/dehydrated/certs/<hostname>/ zur Verfügung, der Docker Host aktualisiert diese per Cronjpb.

### App herunterladen, konfigurieren und starten

* Klone dieses Repo auf deinen Dockerhost nach ``/srv/docker``
  * ``cd /srv/docker``
  * ``git clone https://github.com/jolly-jump/linuxmuster-mrbs``
* Wechsle in das App-Verzeichnis: ``cd linuxmuster-mrbs``
* Passe die Werte in der Datei ``mrbs.ini`` an.
* Erzeuge eine Konfiguration mit: ``./deploy/bin/turnkey -c mrbs.ini``
* Starte die App mit dem Befehl ``docker-compose up -d``

Jetzt solltest du dich an deinem MRBS unter der Adresse https://mrbs.meine-schule.de/ anmelden können, so wie du deinen Service-Host und deine Service-Domain gewählt und konfiguriert hast.


