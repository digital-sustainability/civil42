# civil42

## setup

### dynamic calls

```
https://en.wikipedia.org/w/api.php
```

#### jqp

```
https://github.com/sighrobot/jqp?tab=readme-ov-file#how-to-use

https://jqp.vercel.app

Fetch raw data: https://de.wikipedia.org/w/api.php?action=query&format=json&prop=extracts&exintro&explaintext&titles=<TITLES>

Transform response with jq: .query.pages[].extract | gsub("\n*$"; "") | gsub("\n"; "&#x000A;&#x000A;")
```