# civil42

[![arc42 Build with Maven](https://github.com/digital-sustainability/civil42/actions/workflows/maven.yml/badge.svg)](https://github.com/digital-sustainability/civil42/actions/workflows/maven.yml)

[![Deploy Jekyll with GitHub Pages dependencies preinstalled](https://github.com/digital-sustainability/civil42/actions/workflows/jekyll-gh-pages.yml/badge.svg)](https://github.com/digital-sustainability/civil42/actions/workflows/jekyll-gh-pages.yml)

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
