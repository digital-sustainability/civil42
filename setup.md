# setup

## dynamic calls

```
https://en.wikipedia.org/w/api.php
```

## jqp

```
https://github.com/sighrobot/jqp?tab=readme-ov-file#how-to-use

https://jqp.vercel.app

Fetch raw data: https://de.wikipedia.org/w/api.php?action=query&format=json&prop=extracts&exintro&explaintext&titles=<TITLES>

Transform response with jq: .query.pages[].extract | gsub("\n*$"; "") | gsub("\n"; "&#x000A;&#x000A;")
```

## Website description

```
wget -O- -q <URL> | xmllint --html --format 2> /dev/null - | awk '/meta name="description"/{print}'
```

## eMails

```
httrack

grep -EiorhI '([[:alnum:]|\._.-]+@[[:alnum:]_.-]+?\.[[:alpha:].]{2,6})' "$@" * | sort | uniq > emails.txt

cat eMails.txt | wc
```

### Body 

#### 1

Sehr geehrte Damen und Herren
 
Wir – das ist die Fachgruppe «Digital Sustainability Lab» der Berner Fachhochschule – führen zurzeit im Rahmen eines Innovationsschecks eine Umfrage zum Thema "Digitale Souveränität von Vereinen" durch und würden uns freuen, wenn wir Sie (als Verein) hier als Teilnehmer dieser max. 10-minütigen Umfrage gewinnen könnten:
 
https://surveys.bfh.ch/index.php/134196

Vielen Dank für Ihre Zeit und mit freundlichen Grüssen aus Bern,
Markus Tiede
_____________________________________________
Dipl.-Inf. (FH) Markus Tiede
«Digitale Transparenz & Offenheit unternehmerisch gelebt - so gehen wir gemeinsam & souverän in eine nachhaltige Zukunft. 🌱»
 
Berner Fachhochschule, Departement Wirtschaft
Institut Public Sector Transformation
Brückenstrasse 73, CH-3005 Bern
https://www.bfh.ch/ipst
 
Direkt +41 31 848 60 35
Mobile +49 152 038 722 51
E-Mail markus.tiede@bfh.ch
Matrix @markus.tiede:matrix.org
https://www.bfh.ch/de/markus-andreas-tiede
