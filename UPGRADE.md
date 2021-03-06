Upgrading Instructions for HBS
==============================

Upgrading from v0.67.1
----------------------

## Prerequisites

- **extended** Hugo.
- **npm**.

## Configuration

The following configuration is required:

```toml
[build]
  writeStats = true
```

> It tells Hugo generate a file named `hugo_stats.json`, used by `postcss` for purging unused CSS.

## Assets

- Move `assets/js/custom.js` to `assets/main/js/custom.ts`.
- Move `assets/css/custom.css` to `assets/main/scss/_custom.scss`.
- Move `assets/css/highlight.css` to `assets/main/scss/_highlight.scss`.

## KaTeX

Move `assets/js/katex.config.js` to `assets/katex/js/options.ts`.

```js
const options = {};
export default options;
```

## Mermaid

Move `assets/js/mermaid.config.js` to `assets/mermaid/js/options.ts`.

```js
const options = {};
export default options;
```

## Viewer

Move `assets/js/viewer.config.js` to `assets/viewer/js/options.ts`.

```js
const options = {};
export default options;
```

## Icons

Add the extra FontAwesome icons in `assets/icons/custom.js`.

```js
// import { faClock } from '@fortawesome/free-solid-svg-icons';
// import { faAddressBook } from '@fortawesome/free-regular-svg-icons';
// import { faAmazon, faGoogle } from '@fortawesome/free-brands-svg-icons';

const icons = [
    // faClock,
    // faAddressBook,
    // faAmazon, faGoogle,
];
export default icons;
```

## Build and Deploy

```shell
$ hugo mod npm pack
$ npm install
$ hugo
```
