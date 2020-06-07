* Live: https://golubitsky.github.io/present/

## Deploy

* Builds are setup via [Travis CI](https://travis-ci.com/github/golubitsky/present) for the `master` branch.
* Builds generate static content in `/docs` based on `slides.md` .
* Travis CI pushes the `gh-pages` branch.
* [Github settings](https://github.com/golubitsky/present/settings) are to build from `gh-pages` .

## Develop

1. Install dependencies

``` sh
npm install
```

2. To generate a static website in the `docs` subdirectory

``` sh
npm run develop
```

3. Open `docs/index.html` 

* Can't get `--watch` to work.
* Available themes: https://github.com/hakimel/reveal.js/tree/master/css/theme/source

## Based On

* [reveal-md](https://github.com/webpro/reveal-md)
