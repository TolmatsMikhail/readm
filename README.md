## Kindiedays

Kindiedays is a web-project for kindergartens.
The application is made for more convenient control of children's attendance of classes, food control, manage children, teachers, activity categories, create reports, menus and much more.

## Installation

Before start, you have to install

* [NodeJS](https://nodejs.org/en/download/) is a JavaScript runtime built on Chrome's V8 JavaScript engine.
* [Bower](https://bower.io/) is a package manager for the web.
* [Ember](https://bower.io/) is project main web-framework.

To install dependencies type this command in root project folder.  

``` bower install && npm install ```

Define namespace in ```app.js```. You can redefine it in every component to customize requset to server.

To connect your local project with server define proxy configuration in ``` package.json ``` file.

Example:

    ...
    {
        "scripts": {
            "start": "ember server --proxy https://YOUR_SERVER.com/"
        }
    }
    ...

Start project locally with terminal command:

``` npm run start ```

After successful build open browser on page  ```http://localhost:4200/```.

## Build and Deploy

### First way

Build your project locally with npm command:

``` npm run build ```

Files from ```dist/``` folder put on you server.

### Second way (as example from own kindiedayz development)

Deploy and build are carried out using [Amazon Web Servive](https://aws.amazon.com/ru/).

Code is stored on the [Bitbucket](bitbucket.org).

Since we deploy the project on AWS we need to deploy the changes on AWS CodeCommit.

AWS CodeCommit is actually just a mirror for Bitbucket repository, so the changes should be done in Bitbucket repository and after that be published in AWS CodeCommit.

To do so you need to generate SSH key - follow step 3 from [this page](https://docs.aws.amazon.com/codecommit/latest/userguide/setting-up-ssh-unixes.html).
Then you need to setup a mirror in your git.

Once you have added your SSH key via AWS IAM (Identity and Access Management) add a remote and git push as with any other git repo.

Check ```.git/config``` file or type in terminal git congif --list.

It should looks as follows for the codecommit remote:

```
    [remote "codecommit"]
    url = ssh://git-codecommit.eu-west-1.amazonaws.com/v1/repos/kindiedays-repository
    fetch = +refs/heads/*:refs/remotes/origin/*
```

## Documentation

You can find the Ember documentation [on this website](https://www.emberjs.com/).
Project uses Ember v.2.3.2

## Services you often may use

### Translate

To use different languages in project, look at ```app/locales``` folder.

To get new languange support create a new folder with config.js, translations.js and translations.json files in.

Important! Every file's keys have to be equal for all folders in ```app/locales```.

To overview visit ```top-navigation.js```.

### Date and time

Application use [moment](http://momentjs.com/docs/) to get dates, convert dates and do other different manipulation with Date object.

### Bootstrap

Bootstrap is an open source toolkit for developing with HTML, CSS, and JS. See [documentation](http://getbootstrap.com) for details.

###  Notify user

* Line-style notification.

Usage examples:

Success notification with translate:

```CONTEXT.get('flashMessages').success(CONTEXT.get('i18n').t('place.saved'))```

Error notification with translate:

```CONTEXT.get('flashMessages').danger(CONTEXT.get('i18n').t('place.saved'))```

Combine notifications with translate:

```CONTEXT.get('flashMessages').add(CONTEXT.get('i18n').t('place.saved'))```

Remove notification:

```CONTEXT.get('flashMessages').clearMessages()```

* Toaster style notification. See [PNotify documentation](https://sciactive.com/pnotify/)

Define PNotify ```/* global PNotify */``` in your controller/service.

Usage examples:

```
new PNotify({
    text: this.get('i18n').t('dailyReport.activityCategory.saved'),
    type: 'success',
    delay: 2500
})
```

## Styles

Feel free to use default Bootstrap styles.
Also you can add your own components' styles to file ``` app/styles/app.css ```

## Assets - fonts and images

Web-fonts and images are stored in ``` public/assets```
