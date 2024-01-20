# Windows Setup – FiveM

Installiert XAMPP (neueste Version = ganz unten) unter: https://www.apachefriends.org/de/download.html

// Wenn eine Meldung kommt, einfach ignorieren! 

Bei Select Components haken wegmachen bei:
-Filezilla FTP Server /Mercury Mail Server /Tomcat / Perl / Webalizer /Fake Sendmail

Starte Apache und MySQL (XAMPP)
Drückt bei MySQL auf [Admin] und schaut, ob die Datenbank erreichbar ist!


Geht auf: https://runtime.fivem.net/artifacts/fivem/build_server_windows/master/
Und lädt die (neueste) Version herunter! [Latest Recommended]

Erstellt auf euer Festplatte einen Ordner: FXServer
und in den Ordner erstellt ihr noch einen mit den namen = server! ( FxServer/server)

Und dort kommen die ganzen Sachen rein, die ihr heruntergeladen habt (server.7z)
Führt anschließend FXServer aus! [Ordner=server]

Wenn sich eine Webseite öffnet, gibt ihr dort den Code ein, der für euch zur Verfügung steht in FXServer.exe

Loggt euch ein mit eurem CFX oder PATREON Account.
Erstellt einen BACKUP Passwort eurer Wahl.

Der nächste Schritt ist selbst erklärend.
- Server Name
-Deployment Type = Local Server Data
// Erstellt im Ordner [FxServer] einen Ordner mit server-data und anschließend (im Ordner server-data) einen Ordner mit resources und server.cfg! Öffnet die Server.cfg und gibt das ein: https://docs.fivem.net/docs/server-manual/setting-up-a-server-vanilla/#windows [Nur das, was im grauen Fenster ist, man sieht es!] //
gibt dann z. B. ein C:\FXServer\server-data
danach C:\FXServer\server-data\server.cfg

Geht in den server.cfg:
Und ändert euren Steam webapikey unter: https://steamcommunity.com/dev/apikey
set steam_webApiKey
und euren Lizenz Key unter: https://keymaster.fivem.net/
sv_licenseKey
Wenn ihr wollt, könnt ihr noch euren Hostname ändern unter sv_hostname, sv_projectName, sv_projectDesc (Kann man aber auch später machen)
sets locale > sets locale "de-DE"



## PORTS FREISCHALTEN

Windows Server FiveM Installieren [Schritt 3] – [Ports freischalten]
Sucht nach: Windows Defender Firewall mit erweiterter Sicherheit und öffnet diese.

Geht auf eingehende Regeln > Neue Regel > Port > (TCP) 30120, 40120 > 2x weiter > Name: FiveM Ports (etc.)
Geht auf ausgehende Regeln > Neue Regel > Port > (TCP) 30120, 40120 > Verbindung zulassen > Name: (Fivem/Txadmin) etc.

Bleibt bei ausgehende Regeln > Neue Regel > Port > UDP > 30120 > Verbindung zulassen > Name: FiveM
Eingehende Regeln > Neue Regel > Port > UDP > 30120 > Verbindung zulassen > Name: FiveM