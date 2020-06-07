* Builds are setup via [Travis CI](https://travis-ci.com/github/golubitsky/present) for the `master` branch.

* Builds generate static content in `/docs` based on `slides.md` .
* Travis CI pushes the `gh-pages` branch.
* [Github settings](https://github.com/golubitsky/present/settings) are to build from `gh-pages` .
* Builds deploy to: https://golubitsky.github.io/present/

* Based on [reveal-md](https://github.com/webpro/reveal-md)

## Development

Available themes: https://github.com/hakimel/reveal.js/tree/master/css/theme/source

``` 
npm install
```

then to serve and open the presentation in a browser

``` 
npm run presentation
```

or to generate a static website in the `docs` subdirectory

``` 
npm run generate
```

Gratitude: [this template](https://martinmurphy.github.io/slidestemplate)
