# About Axino

Typescript component library, alternative to frameworks like Vue, React, Angular for front-end app development. Small footprint. Pure HTML5 / CSS / TS.


# Installation (from npm):

npm i axino


# Axino Components API documentation :
https://serge-hulne.github.io/axino-docs


# Tutorials:

https://serge-hulne.medium.com/getting-started-with-axino-4584bcdb99ca

https://serge-hulne.medium.com/axino-vs-vue-js-part-1-the-basics-f58872f54022

https://serge-hulne.medium.com/axino-vs-vue-react-angular-d312fdaf9277

https://serge-hulne.medium.com/axino-electron-desktop-app-9bfd8169b661

https://serge-hulne.medium.com/build-a-desktop-calculator-app-with-axino-and-electron-in-one-minute-459c9d29d72d


# Usage:


### Create a html file (hello.html) to hold the app script:
  
```
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/picnic">
    <title>Axino2 Hello world example</title>
</head>

<body>
    <!-- for testing *.ts sources, via "parcel index.html" -->
    <script src="hello.ts"></script>
</body>


</html>
```


### Create the Typescript file (hello.ts) which codes the apps, using Axino components:
   
```
import { Button } from "axino/button";
import { log } from "axino/core";
import { Label } from "axino/label";
import { Div } from "axino/div";


// Create a basic Div:
var d = new Div(null);
d.appendToApp();
d.vertical();

// Add a label to the Div:
var l = new Label("Clik on B1");
l.appendTo(d);

// Create a Button add to Div:
var b1 = new Button("B1");
b1.appendTo(d);

// Add behaviour to Button b (which acts on label l):
b1.onClick(() => {
    l.setText("<h1>Hello World!</h1>");
    log(l.getText());
});
```


### To test the app:
```   
parcel hello.html
```

(Parcel bundles the TS files into a single JS file and starts a local server on http://localhost:1234/)
Parcel doc : https://parceljs.org/


### To build the app:
```   
parcel build hello.html
```


### Testing and building the app using package.json
By adding the following to the package.json scripts section of the app

```
  "scripts": {
    "test": "parcel index.html",
    "build": "parcel build index.html"
  }
```
testing and building of the app can be launched as follows:
```
npm run test
```
and
```
npm run build 
```
respectively.

(C) Serge Hulne, 2020.