<img src="https://avatars.githubusercontent.com/u/61867156?s=200&v=4" align="right" width="130">

# Project title
Short description about the project (Business case)

<hr>

## Table of Contents

1. [About the project](#about-the-project)
1. [Run application](#run-application)
    1. [Requirements](#requirements)
    1. [Setup for Mac](#setup-for-mac)
    1. [Run E2E tests](#run-e2e-tests)
1. [Additional info](#additional-info)
    1. [Fastlane setup](#fastlane-setup)
    1. [Sentry setup](#sentry-setup)
3. [Coding conventions](#coding-conventions)
    1. [Project structure](#project-structure)
    1. [How to run tests?](#how-to-run-tests)
    1. [How to run lint?](#how-to-run-lint)
1. [Useful links](#useful-links)
1. [Git conventions](#git-conventions)
1. [Troubleshooting](#troubleshooting)

## About the project 

This is boilerplate.


## Run application

### Requirements

- Yarn
- Node

**NOTE:** We always use **Yarn** as our default package manager tool.

```bash
// start development server
yarn start

// run ios app
yarn ios

// run android app
yarn android
```

### Setup for Mac

> **PRO TIP:** Make sure you’re connected to the internet!🙃

Open your terminal or run it inside this project's integrated terminal:

```bash
git --version

/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"

chmod -R 777 ./scripts
./scripts/reactNativeStarterPack.sh
```

**NOTE:** Script doesn't cover Xcode installation so you have to grab it from [here.](https://developer.apple.com/xcode/resources/)

### Run E2E tests

```
yarn test-e2e
```

## Additional info

- For application monitoring and error tracking we're using [Sentry](https://docs.sentry.io/)
- For deployments and releases we're using [Fastlane](https://docs.fastlane.tools/)
- For navigation we're using [react-native-router-flux](https://www.npmjs.com/package/react-native-router-flux), you can find demo navigation example on `src/containers/Routes.js`
- Localization support is also included in the boilerplate

### Fastlane setup:

1. _fastlane/**Matchfile:**_ Enter your `app_identifier`
   e.g. _com.nfq.projectname_
2. _fastlane/**Fastline:**_ Enter your app name to fields `workspace` and `scheme` and edit path to firebase config script.
3. _fastlane/**Appfile:**_ Add your `app_identifier` and `package_name`
   e.g. _app_identifier("com.nfq.projectname")_ and _package_name("com.nfqprojectname")_

### Sentry setup:

1. Fill in your project name `defaults.project=<your-project-name>` at _**ios/sentry.properties:**_ and _**android/sentry.properties:**_

**Managing locales:**

We're currently using [i18next](https://www.i18next.com/) with [react-i18next](https://react.i18next.com/). Boilerplate includes a working locale demo with language change handler.

Changing language is easy:

```
import { locale } from 'src/utils/locale';

const languageHandler = (lang) => {
    locale.changeLanguage(lang);
}
```

Locale config can be found in `src/utils/locale/`. Language files are located at `src/assets/locale/`.

## Coding conventions

### Naming

#### Event emmiters
`on<event-name>`, e.g.: `onChange`, `onSubmitClick` etc

#### Event handlers
`handle<event-name>`, e.g.: `handleChange`, `handleSubmitClick` etc

#### Variables
Avoid shortened variable names:
* use `option` instead of `opt`
* use `event` instead of `e` or `evt`
* use `nextLevelButton` instead of `nextLvlBtn` or `nxtLevelButt`
* exceptions:
    * common shortenings that are used in everyday language, such as "config", "admin" etc
    * `for` loop variables (`i`, `j` etc)

### Project Structure

#### assets/icons
Any new icon should be placed in `assets/icons` folder. And should be in `svg` format. And run the script

```
yarn svg:icons
```

This script will:

1. Optimize and replace all svg files
1. Overwrite `assets/icons/index.ts` file and add export or update exports

### How to run tests?

```
yarn test
```

### How to run lint?

```
yarn lint
```

## Useful links

- Check Next.js Docs, they are very useful.
- Styled Components
- Atomic design
- [Painless React Native Setup for Mac](https://shift.infinite.red/painless-react-native-setup-for-mac-windows-linux-956c23d2abf9)
- [Fastlane setup](https://carloscuesta.me/blog/shipping-react-native-apps-with-fastlane/)


## Git conventions

Branches should be named in a following manner:

```bash
// new feature
git checkout -b feature/<JiraID (if exists)>-comprehensible-name

// refactoring
git checkout -b refactoring/<JiraID (if exists)>-comprehensible-name

// bugfix
git checkout -b fix/<JiraID (if exists)>-comprehensible-name

// dependency updates
git checkout -b update/<JiraID (if exists)>-package-name
git checkout -b update/<JiraID(if exists)>-other-comprehensible-name
```

Make sure that for every bigger change you have checked out to new branch.
Same goes for complicated package updates (e.g. `react-native`). Also make
sure to be on the new branch when changing something inside native projects
(namely `ios` and `android` directories).


## Troubleshooting

Here we add troubleshooting tips if something needs more setup or one of the module is not working properly.

If you have encountered some problem and managed to fix it please leave a comment.
Comment should be written in following manner:

1. Node module name with version (for example: `react-native@0.50.0`)
1. Error name or text
1. Platform [`ios`, `android`]
1. Steps to reproduce (if there is some)
1. Solution or link to solution

## Test Data
Here is some test data

### Login credentials
```
tester@example.com
test1234
```
---
