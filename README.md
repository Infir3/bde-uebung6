## Überblick
In diesem Beispiel wird ein oozie-Workflow mit Coordinator gestartet. Dazu wird der MapReduce-Job aus Übung 3 verwendet.

## Anleitung
Im HDFS muss die Datei beer_data.txt in das Verzeichnis /input kopiert werden. Das Verzeichnis /output darf noch nicht vorhanden sein.

Oozie-Ordner ins HDFS kopieren:
```
hdfs dfs -put oozie /user/root/oozie
```

Oozie starten:
```
oozie job -oozie http://sandbox.hortonworks.com:11000/oozie -config job.properties -run
```

Den Fortschritt kann man sich im Webinterface auf http://sandbox.hortonworks.com:11000/oozie ansehen.

## Update
Der erste Versuch oben funktioniert leider nicht richtig, es gibt immer einen Fehler mit dem inputPath - irgendwie kann die Datei für den MapReduce-Job nicht richtig vom HDFS gelesen werden.

Danach habe ich es mit einem Beispiel aus dem Hortonworks-Forum probiert: https://community.hortonworks.com/articles/27497/oozie-coordinator-and-based-on-input-data-events.html
Dabei soll ein Verzeichnis mithilfe des Coordinators überwacht werden und sobald neue Inputdateien mit einem bestimmten Format da sind, sollen diese in das Ausgabeverzeichnis kopiert werden.

Die entsprechenden Dateien sind im Ordner *oozie2*. Allerdings gibt es auch hier einen Fehler beim Ausführen des Shell-Scripts ("Failing Job due to failed action [shell-node]") und an dieser Stelle habe ich dann aufgegeben.
