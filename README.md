# md-pdf-converter
MARKDOWN TO PDF CONVERTER

_Unexpected use of pug... #why [help.](https://codeburst.io/what-is-pug-js-jade-and-how-can-we-use-it-within-a-node-js-web-application-69a092d388eb)_

### Wireframe
![wireframe](/wireframe.png)

### How I initiated project:
```bash
npm init
npm install express-generator -g
npm install --save-dev nodemon
npm install --save serve-favicon
express
npm install
DEBUG=md-pdf-converter:* & nodemon ./bin/www
```

Navigate to [http://localhost:3000](http://localhost:3000).

### What is in package.json? [(from here)](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/skeleton_website)
- nodemon: _nodemon is like the node --watch if node had a watch flag_
- body-parser: This parses the body portion of an incoming HTTP request and makes it easier to extract different parts of the contained information. For example, you can use this to read POST parameters.
- cookie-parser: Used to parse the cookie header and populate req.cookies (essentially provides a convenient method for accessing cookie information).
- debug: A tiny node debugging utility modelled after node core's debugging technique.
- morgan: An HTTP request logger middleware for node.
- serve-favicon: Node middleware for serving a favicon (this is the icon used to represent the site inside the browser tab, bookmarks, etc.).


### For Future Reference (When putting in container): How to get on machine and run.
```bash

```

### Plan
1. Web page served by express, put in container, on an EC2 instance.
2. When user uploads document or text, send to server.
3. Server (AWS) should use lambda and step functions to check if it is valid markdown/harmless.
4. Then proceed to turn into pdf.
5. Once step function is complete place the output into an s3 bucket and send client link to download pdf.
6. Client/app served by express should take response and place in correct link or start download.