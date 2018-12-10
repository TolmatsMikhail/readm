## Kindiedays

Kindiedays is a web-project for kindergartens.
The application is made for more convenient control of children's attendance of classes, food control, manage children, teachers, activity categories, create reports, menus and much more.

## Installation

Before start, you have to install

* [NodeJS](https://nodejs.org/en/download/) is a JavaScript runtime built on Chrome's V8 JavaScript engine.
* [Bower](https://bower.io/) is a package manager for the web.
* [Ember](https://bower.io/) is project main web-framework.

To install dependencies type this command in root project folder.  

``` npm install ```

Define namespace in ```app.js```. You can redefine in you component.

To connect your local project with server define proxy configuration in ``` package.json ``` file.
Example:

    ...
    {
        "scripts": {
            "start": "ember server --proxy https://YOUR_SERVE.com/"
        }
    }
    ...

Start project terminal command:

``` npm run start ```

After successful build open browser on page  ```http://localhost:4200/```

## Building

Build project with terminal command:
``` npm run build ```

## Documentation

You can find the Ember documentation [on this website](https://www.emberjs.com/).
Project uses Ember v.2.3.2

## Services you may use often

### Translate

To use different languages in project, look at ```app/locales```.
To get new languange support create a new folder with config.js, translations.js and translations.json files.
Important! Every file keys have to be equal for all folders in ```app/locales```.

### Date and time

Application use [moment](http://momentjs.com/docs/)

### Bootstrap

Bootstrap is an open source toolkit for developing with HTML, CSS, and JS. See [documentation](http://getbootstrap.com)
