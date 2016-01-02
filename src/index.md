---
template: index.html
---

## Getting Started

1. Install NodeJS
1. Create a directory

  ``` bash
  mkdir website
  cd website
  ```

2. Install Metalsmith and dependencies

  ```bash
  npm install metalsmith
  npm install metalsmith-markdown
  ```

3. Create a build.js

  ```js
  var Metalsmith   = require('metalsmith');
  var markdown     = require('metalsmith-markdown');
  Metalsmith(__dirname)
    .use(markdown())
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
  template: site.html
  ---

  # Home Page

  This is a your first page

  ```

6. Create your first template

  Create a directory for a template

  ```bash
    cd..
    mkdir templates
    cd templates
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
    {{ content | safe }}
  </body>
  </html>
  ```

---
---
