# qgm-linuxmuster-docker-mrbs

MRBS Docker App für linuxmuster. 

TESTVERSION - **NICHT PRODUKTIV VERWENDEN**

## Verwendung

* Klone dieses Repo auf deinen Dockerhost, z.B nach /srv/
  * ``cd /srv/``
  * ``git clone https://github.com/qgmgit/qgm-linuxmuster-docker-mrbs.git``
  * Optional kann man das etwas sperrige Verzeichnis umbenennen: ``mv https://github.com/qgmgit/qgm-linuxmuster-docker-mrbs.git linuxmuster-mrbs``
* Wechsle in das Verzeichnis: ``cd linuxmuster-mrbs``
* Passe die Werte in der Datei ``mrbs.ini`` an.
* Erzeuge eine Konfiguration mit: ``./deploy/bin/turnkey -c mrbs.ini``
* Starte die App mit dem Befehl ``docker-compose up -d``

Die Testversion öffnet auf den Docker-Host den Port 8889, du solltest dein MRBS jetzt also unter http://<deine_ip_oder_hostname>:8889 erreichen können.
