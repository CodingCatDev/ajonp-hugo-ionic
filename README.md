# AJonP - Hugo Ionic Theme
[![AJonP Hugo Ionic Theme](https://res.cloudinary.com/ajonp/image/upload/f_auto/v1543792067/ajonp-ajonp-com/ajonp-hugo-theme/aj_on_hugo_ionic.png)](https://ajonp.com/lessons/4-hugo-ionic/)

# Features

## Lesson for use
[AJonP Hugo Ionic Theme](https://ajonp.com/lessons/4-hugo-ionic/)

## Tools

- [Hugo](https://gohugo.io/)
- [Ionic](https://ionicframework.com/)
- [Font Awesome](https://fontawesome.com/)
- [PWA](https://developers.google.com/web/progressive-web-apps/)
- [Algolia](https://www.algolia.com/)

## Orienations

### Phone
![Phone](https://res.cloudinary.com/ajonp/image/upload/v1543790485/ajonp-ajonp-com/ajonp-hugo-theme/ajonp-hugo-theme-phone.png)

### Tablet
![Tablet](https://res.cloudinary.com/ajonp/image/upload/v1543790485/ajonp-ajonp-com/ajonp-hugo-theme/ajonp-hugo-theme-tablet.png)

### Desktop
![Desktop](https://res.cloudinary.com/ajonp/image/upload/v1543790485/ajonp-ajonp-com/ajonp-hugo-theme/ajonp-hugo-theme-desktop.png)

## PWA / Algolia
In order to have these items work there are a few additional considerations, starting with [Netlify - Victor Hugo Template](https://github.com/netlify-templates/victor-hugo).

### Algolia support
package.json - devDependencies
```json
"atomic-algolia": "^0.3.15",
```
package.json - scripts
```json
"algolia": "atomic-algolia",
```

### PWA support
package.json - devDependencies
```json
"sw-precache": "^5.2.1",
```
package.json - scripts
```json
"generate-service-worker": "gulp generate-service-worker"
```
gulpfile.babel.js
```js
// sw-precache
gulp.task('generate-service-worker', function(callback) {
  var swPrecache = require('sw-precache');
  var rootDir = 'dist';

  swPrecache.write(`${rootDir}/service-worker.js`, {
    staticFileGlobs: [rootDir + '/**/*.{js,html,css,png,jpg,gif,svg,eot,ttf,woff}'],
    stripPrefix: rootDir
  }, callback);
});
```