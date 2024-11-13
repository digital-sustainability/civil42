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
cat Q0102-1.csv | uplot bar -H -d ',' -o -t "Das Konzept 'Digitale Souveränität' ist bei unserem Verein sehr... bekannt" --xlabel "n=$(wc -l < Q0102-1-raw.csv)" > Q0102-1.output
```

## Q0102-2

```
csvcut -x -l -c 7 results/survey.csv > Q0102-2-raw.csv
```

```
cat Q0102-2-raw.csv | csvsql - --query "SELECT relevant,COUNT(*) FROM stdin WHERE relevant IS NOT NULL GROUP BY relevant" > Q0102-2.csv
```

```
cat Q0102-2.csv | uplot bar -H -d ',' -o -t "Das Konzept 'Digitale Souveränität' ist bei unserem Verein sehr... relevant" --xlabel "n=$(wc -l < Q0102-2-raw.csv)" > Q0102-2.output
```

## Q0102-3

```
csvcut -x -l -c 8 results/survey.csv > Q0102-3-raw.csv
```

```
cat Q0102-3-raw.csv | csvsql - --query "SELECT angewandt,COUNT(*) FROM stdin WHERE angewandt IS NOT NULL GROUP BY angewandt" > Q0102-3.csv
```

```
cat Q0102-3.csv | uplot bar -H -d ',' -o -t "Das Konzept 'Digitale Souveränität' ist bei unserem Verein sehr... angewandt" --xlabel "n=$(wc -l < Q0102-3-raw.csv)" > Q0102-3.output
```
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