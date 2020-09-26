# Analytics plugins

Durch aktivieren des plugins werden anonyme Performance Daten von den Browsern der Besucher gesammelt.
Dieser werden im Hintergrund an das REDAXO Backend übertragen.

Die Daten werden durch den mitgelieferten Cronjob verdichtet und in der Strukturverwaltung angezeigt.

Das Plugin ist inbesondere dann sinnvoll, wenn man diese Performance Daten nicht über externe Dienste ermitteln möchte (z.B. Google Analytics).
Da keinerlei personalisierte Daten gesammelt werden, gibt es keine DSGVO relevanten details zu beachten.

## Setup

Sobald das plugin aktiviert ist, wird im Frontend Daten gesammelt.

Damit die Daten ausgewertet werden, muss der cronjob vom typ `rex_analytics_cronjob` eingerichtet werden.
Der Cronjob analysiert die gesammelten Rohdaten und sorgt dafür dass diese zusammengefasst im Backend für den Redakteur dargestellt werden.
Im Frontend gesammelte Daten fließen erst in die Anzeige im Backend ein, nachdem der Cronjob gelaufen ist.

## Klassifizierung der Messwerte

Die gesammelten Daten werden nach den Empfehlungen von https://web.dev/vitals/ klassifiziert und in die Kategorien "Good" (Grün), "Needs Improvement" (Gelb) und "Poor" (Rot) einsortiert.

Nicht alle Browser liefern alle Rohdaten. Zum testen arbeitet man am besten mit Google Chrome da dieser bisher die meisten auswertbaren Daten liefert.

## Relevantes

https://web.dev/vitals/ - Webvitals Grundlagen
https://github.com/GoogleChrome/web-vitals - Javascript library zur ermittlung der Rohdaten