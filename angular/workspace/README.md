`first-app` is a normal angular cli application which includes the `second-app``

`second-app` is enhanced with `ngx-build-plus`, so that it can be bootstrapped on a document that already has another Angular application loaded.

To run:
 
 - start the `second-app` first: `npm run start:second`
 - then start the `first-app`:  `npm run start:first`
 
 
 Production build: There is a `index.html` in `dist`, which includes both Angular apps.
 
 - build the `first-app`: `npm run build:first`
 - build the `second-app`: `npm run build:second`
 - `npm run serve:prod`
  
 
Note: Angular relies on `zone.js`, which can only be loaded once on the document.

In development each app brings its own `zone.js`.  

Since versions 0.8.27 `zone.js` does not throw an error when it detects that it is already loaded, but just does nothing ...
Enabling the error is opt-in, see the script block in `first-app/src/index.html`.

The flag `single-bundle true` of `ngx-build-plus` does not bundle polifills and `zone.js`. 
