# Spiele mit Python

Dies ist das Projekt um meinem Sohn etwas Programmierung beizubringen.

Wir nutzen dazu das Buch "Spiele mit Python supereasy programmieren"

## Installation

### Voraussetzungen

Ich habe zunächst python 3.6 und 3.7 deinstalliert und Python 3.8.3 auf dem Mac installiert.

Achtung: Python in der Version 2.7 wird von MacOS mitgebracht, diese also besser stehen lassen.

Im Verzeichnis `/Library/Frameworks/Python.framework/Versions/` nach pygame oder pgzero suchen und diese löschen.

pygame braucht einige Voraussetzungen außerhalb der Pythonwelt, die wir über homebrew installieren müssen. Zunächst müssen wir also
prüfen, ob wir homebrew auf dem Mac haben. Einfach `brew` in die shell eingeben und prüfen, ob der Befehl gefunden wird.

Falls nein müssen wir zunächst homebrew installieren. Dies geschieht über:

```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Das ist ein sehr langerwieriger Installationsprozess. Wir müssen mehrfach das Adminpasswort eingeben. Im Taskmanager verfolgen wir, ob die update Programme noch CPU ziehen bzw. Netzbandbreite belegen (so lange auf jeden Fall in Ruhe lassen).


### Aufbau einer virtual environment

Wir bauen die notwendigen Voraussetzungen für die Programmierlernumgebung in einer eigenen virtual
environment auf, so dass andere python Projekte nicht beeinflusst werden.

Dann habe bin ich in das Verzeichnis ~/development/Linus gegangen und habe dort den Befehl

```
python3 -m venv python-spiele
```

aufgerufen. Damit wurde ein virtuelle python3 Umgebung aufgebaut. Auch wird dabei das Verzeichis `python-spiele` als Projektverzeichnis erzeugt. Wechsel in dieses Verzeichnis und Aufruf von:

```
source ./bin/activate
```

aktiviert dann diese Umgebung.

Anschließend habe ich den pip3 Installationsmanager über `pip3 install --upgrade pip` upgegraded.

### Installation von pygame und pgzero

Leider gibt es Probleme bei der Installation von pygame und pgzero. Die einfache default Installation über pip liefert Fehlermeldungen. Und auch wenn man alles installiert bekommt, heißt das noch nicht, dass das Programm dann funktioniert.

Zunächst also die Voraussetzungen von pygame über homebrew schaffen:

```
brew install sdl2 sdl2_gfx sdl2_image sdl2_mixer sdl2_net sdl2_ttf
```

Die default Version von pygame funktioniert nicht mit python 3.8.3. Daher die Entwicklungsversion installieren über:
```
pip3 install pygame==2.0.0.dev4
```

Nun kann man pgzero ganz einfach installieren.

```
pip3 install pgzero
```

Test der Installation über eine leere Datei `intro.py`. Der Befehl `pgzrun intro.py` soll ein leeres Fenster öffnen.

Danach kann man folgendes in die intro.py Datei eintragen:

```python
# intro.py
WIDTH = 300
HEIGHT = 300

def draw():
    screen.fill((128, 0, 0))
```

Dann sollte `pgzrun intro.py` ein leeres rotes Quadrat anzeigen.

Nun kann es mit der Programmierung für meinen Sohn losgehen.
