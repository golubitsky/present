[![Build Status](https://travis-ci.com/golubitsky/present.svg?branch=master)](https://travis-ci.com/golubitsky/refactoring)  
([live](https://golubitsky.github.io/refactoring/))

### Develop

1. Install dependencies

``` sh
npm install
```

2. To continuously generate a static website in the `docs` subdirectory

``` sh
 npm run develop
```

3. Reload `docs/index.html` 

### Deploy

* Builds are setup via [Travis CI](https://travis-ci.com/github/golubitsky/refactoring) for the `master` branch.
* Builds generate static content in `/docs` based on `slides.md` .
* Travis CI pushes the `gh-pages` branch.
* [Github settings](https://github.com/golubitsky/present/settings) are to build from `gh-pages` .

## Based on [reveal-md](https://github.com/webpro/reveal-md)

### Notes on the framework

* Speaker notes: https://github.com/webpro/reveal-md/#speaker-notes
  + Start with `Note:` -- at the _end_ of a slide.
  + View by pressing `s` during presentation.
* Slide overview: `o` during presentation.
* Multiple animations per slide -> [fragments (not supported in md)](https://revealjs.com/fragments/)
  + surround with: `<!-- .element: class="fragment" -->` 
* Available themes: https://github.com/hakimel/reveal.js/tree/master/css/theme/source

### Bugs with the framework

* Can't get `--css styles.css` to work in Github Pages (works locally). Workaround: `<styles>` tag in `slides.md` .
* Can't get `--watch` to work.
