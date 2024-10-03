
# Architecture Ref.Card 02 - React Application (serverless)

Link zur Übersicht<br/>
https://gitlab.com/bbwrl/m346-ref-card-overview

## Installation der benötigten Werkzeuge

Für das Bauen der App wird Node bzw. npm benötigt. Die Tools sind unter 
der folgenden URL zu finden. Für die meisten Benutzer:innen empfiehlt sich 
die LTS Version.<br/>
https://nodejs.org/en/download/

Node Version Manager<br/>
Für erfahren Benutzer:innen empfiehlt sich die Installation des 
Node Version Manager nvm. Dieses Tool erlaubt das Installiert und das 
Wechseln der Node Version über die Kommandozeile.<br/>
**Achtung: Node darf noch nicht auf dem Computer installiert sein.**<br/>
https://learn2torials.com/a/how-to-install-nvm


## Inbetriebnahme auf eigenem Computer

Projekt herunterladen<br/>
```git clone git@gitlab.com:bbwrl/m346-ref-card-02.git```
<br/>
```cd architecture-refcard-02```

### Projekt bauen und starten
Die Ausführung der Befehle erfolgt im Projektordner

Builden mit Node/npm<br/>
```$ npm install```

Das Projekt wird gebaut und die entsprechenden Dateien unter dem Ordner node_modules gespeichert.

Die App kann nun mit folgendem Befehl gestartet werden<br/>
```$ npm start```

Die App kann nun im Browser unter der URL http://localhost:3000 betrachtet werden.



### Inbetriebnahme mit Docker Container

### Inbetriebnahme mit Docker Container
Als erstes ein Dockerfile erstellen im Hauptordner

![Alt-Text](pictures/img.png)

### Git-Hub Actions YAML-Datei erstellen
Das File muss in im Ordner .github/workflows sein welche neu erstellt werden müssen.

![Alt-Text](pictures/img_1.png)
![Alt-Text](pictures/img_2.png)

### Auf Dockerhub Access-Token erstellen

![Alt-Text](pictures/img_4.png)

### Token auf Git tun
Der Token muss dann auf git hinterlassen werden unter Secrets und der Name muss dann auch im YML file sein

![Alt-Text](pictures/img_5.png)

### File pushen auf Git
Dann ist es unter Actions ersichtlich

![Alt-Text](pictures/img_3.png)

### Log in to Aws 

Als erstes auf AWS einlogge und "aws_access_key_id", "aws_secret_access_key" und "aws_session_token" kopieren und auf github als secret speichern. Aber die Region nicht vergessen

![Alt-Text](pictures/img_6.png)

![img.png](img.png)

### ECR erstellen

Auf ECR gehen und danach die ECR erstellen, hier sind keine Konfigurationen nötig, nur der Name

![img_5.png](img_5.png)

### ECS-Cluster erstellen

Ein Cluster erstellen, Namen geben und auf AWS Fargate lassen

![img_1.png](img_1.png)

### Aufgabendefinition erstellen

Auf "neue Aufgabendefinition erstellen" drücken und Schritt für Schritt alles angeben

Zuerst Namen geben und AWS-Fargate auswählen

![img_2.png](img_2.png)

LabRole auswählen

![img_3.png](img_3.png)

Bei der Aufgabendefinition noch die Image url von ECR angeben, entrypoint hineinschreiben und den Port angeben 

![img_4.png](img_4.png)

### ECS-Service erstellen

Bei Beretstellen auf Service erstellen klicken

![img_6.png](img_6.png)

Cluster auswählen oben und danach
den Namen angeben. Dann Service erstellen.

![img_7.png](img_7.png)

### Github Actions

Nach dem pushen siet man das auf GutHub Actions

![img_8.png](img_8.png)

### Image auf ECR

![img_9.png](img_9.png)

### Überprüfung

Um zu schauen ob alles geklappt hat kann man hier klicken und die Seite sehen

![img_10.png](img_10.png)



