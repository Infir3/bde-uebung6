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
