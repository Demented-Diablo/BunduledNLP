# compromise.min.js (Browser-ready NLP Bundle)

This repo contains a **minified browser bundle** of the [`compromise`](https://github.com/spencermountain/compromise) NLP library, created using [esbuild](https://esbuild.github.io/).

## 🔍 Why this exists

The official Compromise package on npm does not include a prebuilt `compromise.min.js` file for direct use in **browser environments** (like Chrome Extensions or frontend-only apps). This repo provides a plug-and-play version for developers who want to:

- Use Compromise without a bundler (e.g., in a `<script>` tag)
- Load NLP functionality directly into `window.nlp` inside browser scripts

## 📦 File Contents

- `compromise-bundle.min.js`  
  The minified browser-compatible bundle built from `compromise@14.14.4` using esbuild.

## 🛠 How to Use

1. Download `compromise-bundle.min.js`  
2. Include it in your HTML or Chrome Extension `manifest.json`:

```html
<script src="compromise-bundle.min.js"></script>
<script>
  const doc = nlp("hello world");
  console.log(doc.nouns().out('array'));
</script>


Built Using

npx esbuild compromise-index.js \
  --bundle \
  --minify \
  --format=iife \
  --global-name=nlp \
  --outfile=compromise-bundle.min.js

  
This bundle respects the original MIT license of the compromise library. This repo simply provides a precompiled build for developer convenience.
