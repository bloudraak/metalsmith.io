---
template: index.html
---

## Getting Started

Metalsmith was written using [NodeJS](https://nodejs.org/en/). You can verify whether you have NodeJS installed by typing the following into a terminal window (or command prompt if you use Microsoft Windows).

	node --version
	npm --version

If the version being printed exceeds v4.0.0, then we’re in business, otherwise follow the instructions in the [NodeJS](https://nodejs.org/en/) site and install Node. We’ll be waiting for you.


1. Create a directory

  ``` bash
  mkdir website
  cd website
  ```

2. Install Metalsmith and dependencies

  ```bash
	npm init
  npm install --save metalsmith
  npm install --save metalsmith-markdown
  npm install --save metalsmith-layouts
	npm install --save handlebars
  ```

3. Create a index.js

```js
var Metalsmith   = require('metalsmith');
var markdown     = require('metalsmith-markdown');
var layouts      = require('metalsmith-layouts')

Metalsmith(__dirname)
  .use(markdown())
  .use(layouts('handlebars'))
  .destination('./build')
  .build(function(err, files) {
    if (err) { throw err; }
  });
  ```

4. Create a "src" directory

  ```bash
  mkdir src
  cd src
  ```
5. Create your first page (index.md)

  ```markdown
  ---
  title: Home Page
  layouts: site.html
  ---

  # Home Page

  This is a your first page

  ```

6. Create your first template

  Create a directory for a layouts

  ```bash
    cd..
    mkdir layouts
    cd layouts
  ```

  Create a file `site.html`

  ```html
  <html>
  <head>
    <title>{{ title }}</title>
    <meta name="description" content="{{ description }}">
  </head>
  <body>
    <h1>{{ title }}</h1>
    <p>{{ description }}</p>
    {{ content }}
  </body>
  </html>
  ```

7. Build your website

	node index.js



---
---
