# Crafty Controller - Minecraft Server Management

This repository contains the `docker-compose.yml` file to easily set up and run the [Crafty Controller](https://craftycontrol.com/), a web-based control panel for managing Minecraft servers.

Dieses Repository enthält die `docker-compose.yml`-Datei, um den [Crafty Controller](https://craftycontrol.com/) einfach einzurichten und auszuführen, ein webbasiertes Control Panel zur Verwaltung von Minecraft-Servern.

## Prerequisites / Voraussetzungen

Before you begin, ensure you have the following installed:
Stellen Sie sicher, dass Sie Folgendes installiert haben, bevor Sie beginnen:

*   [Docker](https.docs.docker.com/get-docker/)
*   [Docker Compose](https.docs.docker.com/compose/install/)

## Configuration / Konfiguration

The `docker-compose.yml` file is configured to run the latest version of the Crafty Controller.
Die `docker-compose.yml`-Datei ist so konfiguriert, dass die neueste Version des Crafty Controllers ausgeführt wird.

### Ports

*   `8443:8443`: HTTPS access to the Crafty Controller web interface. / HTTPS-Zugriff auf die Weboberfläche des Crafty Controllers.
*   `8123:8123`: Port for Dynmap, if you choose to use it. / Port für Dynmap, falls Sie es verwenden möchten.
*   `19132:19132/udp`: Port for Minecraft Bedrock Edition. / Port für die Minecraft Bedrock Edition.
*   `25500-25600:25500-25600`: Port range for your Minecraft Java Edition servers. / Portbereich für Ihre Minecraft Java Edition-Server.

### Volumes

The following volumes are mapped to your local machine to persist data:
Die folgenden Volumes werden auf Ihrem lokalen Rechner gemappt, um Daten zu speichern:

*   `./backups:/crafty/backups`: Stores server backups. / Speichert Server-Backups.
*   `./logs:/crafty/logs`: Contains logs for the Crafty Controller and your Minecraft servers. / Enthält Protokolle für den Crafty Controller und Ihre Minecraft-Server.
*   `./servers:/crafty/servers`: This is where your Minecraft server files are stored. / Hier werden Ihre Minecraft-Serverdateien gespeichert.
*   `./config:/crafty/app/config`: Holds the configuration files for the Crafty Controller. / Enthält die Konfigurationsdateien für den Crafty Controller.
*   `./import:/crafty/import`: Use this directory to import existing Minecraft servers into Crafty. / Verwenden Sie dieses Verzeichnis, um vorhandene Minecraft-Server in Crafty zu importieren.

## Usage / Verwendung

To start the Crafty Controller, run the following command in the same directory as the `docker-compose.yml` file:
Führen Sie den folgenden Befehl im selben Verzeichnis wie die `docker-compose.yml`-Datei aus, um den Crafty Controller zu starten:

```bash
docker-compose up -d
```

To stop the container, use:
Verwenden Sie zum Stoppen des Containers:

```bash
docker-compose down
```

You can access the Crafty Controller web interface by navigating to `https://localhost:8443` in your web browser.
Sie können auf die Weboberfläche des Crafty Controllers zugreifen, indem Sie in Ihrem Webbrowser zu `https://localhost:8443` navigieren.

## Crafty Controller Features / Funktionen

Crafty Controller provides a wide range of features for managing your Minecraft servers, including:
Crafty Controller bietet eine breite Palette von Funktionen zur Verwaltung Ihrer Minecraft-Server, darunter:

*   **Server Management:** Create, start, stop, and restart your Minecraft servers. / Erstellen, Starten, Stoppen und Neustarten Ihrer Minecraft-Server.
*   **Player Management:** View and manage players on your servers. / Anzeigen und Verwalten von Spielern auf Ihren Servern.
*   **Console Access:** Access the server console directly from the web interface. / Greifen Sie direkt über die Weboberfläche auf die Serverkonsole zu.
*   **File Management:** Easily manage your server files. / Verwalten Sie Ihre Serverdateien einfach.
*   **Automated Backups:** Schedule and manage backups for your servers. / Planen und verwalten Sie Backups für Ihre Server.
*   **Bedrock & Java Edition Support:** Manage both Java and Bedrock servers. / Verwalten Sie sowohl Java- als auch Bedrock-Server.
*   **Docker Support:** Runs seamlessly in a Docker container. / Läuft nahtlos in einem Docker-Container.

## License / Lizenz

The Crafty Controller is open-source software licensed under the [GNU General Public License v3](https://gitlab.com/crafty-controller/crafty-4/-/blob/master/LICENSE).
Der Crafty Controller ist eine Open-Source-Software, die unter der [GNU General Public License v3](https://gitlab.com/crafty-controller/crafty-4/-/blob/master/LICENSE) lizenziert ist.
