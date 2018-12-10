## Kindiedays

Kindiedays is a web-project for kindergartens.
The application is made for more convenient control of children's attendance of classes, food control, manage children, teachers, activity categories, create reports, menus and much more.

## Installation

Before start, you have to install

* [NodeJS](https://nodejs.org/en/download/) is a JavaScript runtime built on Chrome's V8 JavaScript engine.
* [Bower](https://bower.io/) is a package manager for the web.
* [Ember](https://bower.io/) is project main web-framework.

To install dependencies are need to run project, make this command in root project folder.  

``` npm install ```

To connect your local project with server define proxy configuration in ``` package.json ``` file.
Example:

    ...
    {
        "scripts": {
            "start": "ember server --proxy https://YOUR_SERVE.com/"
        }
    }
    ...

Start project with command:

``` npm run start ```
