# Setup

- https://csvkit.readthedocs.io
- https://github.com/red-data-tools/YouPlot?tab=readme-ov-file

## Q0102-1

```
csvcut -x -l -c 6 results/survey.csv > Q0102-1-raw.csv
```

```
cat Q0102-1-raw.csv | csvsql - --query "SELECT bekannt,COUNT(*) FROM stdin WHERE bekannt IS NOT NULL GROUP BY bekannt" > Q0102-1.csv
```

```
cat Q0102-1.csv | uplot bar -H -d ',' -o -t "Das Konzept 'Digitale Souveränität' ist bei unserem Verein... bekannt" --xlabel "n=$(wc -l < Q0102-1-raw.csv)" > Q0102-1.output
```

## Q0102-2

```
csvcut -x -l -c 7 results/survey.csv > Q0102-2-raw.csv
```

```
cat Q0102-2-raw.csv | csvsql - --query "SELECT relevant,COUNT(*) FROM stdin WHERE relevant IS NOT NULL GROUP BY relevant" > Q0102-2.csv
```

```
cat Q0102-2.csv | uplot bar -H -d ',' -o -t "Das Konzept 'Digitale Souveränität' ist bei unserem Verein... relevant" --xlabel "n=$(wc -l < Q0102-2-raw.csv)" > Q0102-2.output
```

## Q0102-3

```
csvcut -x -l -c 8 results/survey.csv > Q0102-3-raw.csv
```

```
cat Q0102-3-raw.csv | csvsql - --query "SELECT angewandt,COUNT(*) FROM stdin WHERE angewandt IS NOT NULL GROUP BY angewandt" > Q0102-3.csv
```

```
cat Q0102-3.csv | uplot bar -H -d ',' -o -t "Das Konzept 'Digitale Souveränität' ist bei unserem Verein... angewandt" --xlabel "n=$(wc -l < Q0102-3-raw.csv)" > Q0102-3.output
```

## Q0103

```
csvcut -x -l -c 9 results/survey.csv > Q0103-raw.csv
```

```
cat Q0103-raw.csv | csvsql - --query "SELECT empfehlungen,COUNT(*) FROM stdin WHERE empfehlungen IS NOT NULL GROUP BY empfehlungen" > Q0103.csv
```

```
cat Q0103.csv | uplot bar -H -d ',' -o -t "Empfehlungen" --xlabel "n=$(wc -l < Q0103-raw.csv)" > Q0103.output
```

## Q0104-1

```
csvcut -x -l -c 10,12,14,16,18,20,22,24,26,28,30,32,34 results/survey.csv > Q0104-1-raw.csv
```

```
cat Q0104-1-raw.csv | csvsql - --query "SELECT
  SUM(CASE WHEN "a" = 1 THEN 1 ELSE 0 END) as 'Kommunizieren',
  SUM(CASE WHEN "b" = 1 THEN 1 ELSE 0 END) as 'Arbeiten planen',
  SUM(CASE WHEN "c" = 1 THEN 1 ELSE 0 END) as 'Vereinsaktivitaeten organisieren',
  SUM(CASE WHEN "d" = 1 THEN 1 ELSE 0 END) as 'Termine planen',
  SUM(CASE WHEN "e" = 1 THEN 1 ELSE 0 END) as 'Dokumente gemeinsam bearbeiten',
  SUM(CASE WHEN "f" = 1 THEN 1 ELSE 0 END) as 'Vereinssoftware',
  SUM(CASE WHEN "g" = 1 THEN 1 ELSE 0 END) as 'Clouds Datenablage',
  SUM(CASE WHEN "h" = 1 THEN 1 ELSE 0 END) as 'Projektmanagement',
  SUM(CASE WHEN "i" = 1 THEN 1 ELSE 0 END) as 'Quiz Umfragen Abstimmungen',
  SUM(CASE WHEN "j" = 1 THEN 1 ELSE 0 END) as 'Ideen Sammeln Kreativ gestalten',
  SUM(CASE WHEN "k" = 1 THEN 1 ELSE 0 END) as 'Videos Designs und Podcasts kreieren',
  SUM(CASE WHEN "l" = 1 THEN 1 ELSE 0 END) as 'Video Konferenzen Online Meetings',
  SUM(CASE WHEN "m" = 1 THEN 1 ELSE 0 END) as 'Websites Video Tutorials Unterlagen'
  FROM stdin" > Q0104-1-pivot.csv
```

manual upivot

```
cat Q0104-1.csv | uplot bar -H -d ',' -o -t "Digitale Tools / Prozesse kommen zum Einsatz" --xlabel "n=$(wc -l < Q0104-1-raw.csv)" > Q0104-1.output
```

## Q0104-2

```
csvcut -x -c 11 results/survey.csv > Q0104-2-raw.csv
```

manual separation & term unify

```
cat Q0104-2.csv | uplot count -H -d ',' -o --xlabel "n=$(wc -l < Q0104-2.csv)" > Q0104-2.output
```


## Q0104-3

```
csvcut -x -c 13 results/survey.csv > Q0104-3-raw.csv
```

manual separation & term unify

```
cat Q0104-3.csv | uplot count -H -d ',' -o --xlabel "n=$(wc -l < Q0104-3.csv)" > Q0104-3.output
```

## Q0104-4

```
csvcut -x -c 15 results/survey.csv > Q0104-4-raw.csv
```

manual separation & term unify

```
cat Q0104-4.csv | uplot count -H -d ',' -o --xlabel "n=$(wc -l < Q0104-4.csv)" > Q0104-4.output
```

## Q0104-5

```
csvcut -x -c 17 results/survey.csv > Q0104-5-raw.csv
```

manual separation & term unify

```
cat Q0104-5.csv | uplot count -H -d ',' -o --xlabel "n=$(wc -l < Q0104-5.csv)" > Q0104-5.output
```

## Q0104-6

```
csvcut -x -c 19 results/survey.csv > Q0104-6-raw.csv
```

manual separation & term unify

```
cat Q0104-6.csv | uplot count -H -d ',' -o --xlabel "n=$(wc -l < Q0104-6.csv)" > Q0104-6.output
```

## Q0104-7

```
csvcut -x -c 21 results/survey.csv > Q0104-7-raw.csv
```

manual separation & term unify

```
cat Q0104-7.csv | uplot count -H -d ',' -o --xlabel "n=$(wc -l < Q0104-7.csv)" > Q0104-7.output
```

## Q0104-8

```
csvcut -x -c 23 results/survey.csv > Q0104-8-raw.csv
```

manual separation & term unify

```
cat Q0104-8.csv | uplot count -H -d ',' -o --xlabel "n=$(wc -l < Q0104-8.csv)" > Q0104-8.output
```

## Q0104-9

```
csvcut -x -c 25 results/survey.csv > Q0104-9-raw.csv
```

manual separation & term unify

```
cat Q0104-9.csv | uplot count -H -d ',' -o --xlabel "n=$(wc -l < Q0104-9.csv)" > Q0104-9.output
```

## Q0104-10

```
csvcut -x -c 27 results/survey.csv > Q0104-10-raw.csv
```

manual separation & term unify

```
cat Q0104-10.csv | uplot count -H -d ',' -o --xlabel "n=$(wc -l < Q0104-10.csv)" > Q0104-10.output
```

## Q0104-11

```
csvcut -x -c 29 results/survey.csv > Q0104-11-raw.csv
```

manual separation & term unify

```
cat Q0104-11.csv | uplot count -H -d ',' -o --xlabel "n=$(wc -l < Q0104-11.csv)" > Q0104-11.output
```

## Q0104-12

```
csvcut -x -c 31 results/survey.csv > Q0104-12-raw.csv
```

manual separation & term unify

```
cat Q0104-12.csv | uplot count -H -d ',' -o --xlabel "n=$(wc -l < Q0104-12.csv)" > Q0104-12.output
```

## Q0104-13

```
csvcut -x -c 33 results/survey.csv > Q0104-13-raw.csv
```

manual separation & term unify

```
cat Q0104-13.csv | uplot count -H -d ',' -o --xlabel "n=$(wc -l < Q0104-13.csv)" > Q0104-13.output
```

## Q0104-14

```
csvcut -x -c 35 results/survey.csv > Q0104-14-raw.csv
```

manual separation & term unify

```
cat Q0104-14.csv | uplot count -H -d ',' -o --xlabel "n=$(wc -l < Q0104-14.csv)" > Q0104-14.output
```

## Q0201

```
csvcut -x -c 38 results/survey.csv > Q0201-raw.csv
```

manual separation & term unify

```
cat Q0201.csv | uplot count -H -d ',' -o --xlabel "n=$(wc -l < Q0201.csv)" > Q0201.output
```

## Q0202

```
csvcut -x -c 39 results/survey.csv > Q0202-raw.csv
```

manual separation & term unify

```
cat Q0202.csv | uplot count -H -d ',' -o --xlabel "n=$(wc -l < Q0202.csv)" > Q0202.output
```

## Q0301

```
csvcut -x -c 40 results/survey.csv > Q0301-raw.csv
```

## Q0301

```
csvcut -x -c 41 results/survey.csv > Q0302-raw.csv
```