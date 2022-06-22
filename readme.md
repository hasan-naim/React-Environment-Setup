
<!-- TABLE OF CONTENTS -->

## To start easily follow this section

run in the terminal 
```
npx create-react-app appName
```

And then create `.eslintrc` file and copy all code from this repo's `.eslintrc` file and past.
And you have to copy one more thing the dev dependencies go to `package.json` file of this repo and copy `devDependencies` and past to your file.
Now run in the terminal

```
npm install
```


<br>



## Table of Contents

- [Project Initialize](#project-initialize)
- [Editor Setup](#editor-setup)
  - [Plugins](#plugins)
  - [Settings](#settings)
  - [Set Line Breaks](#set-line-breaks)
- [Linting Setup](#linting-setup)
  - [Install Dev Dependencies](#install-dev-dependencies)
  - [Create Linting Configuration file manually](#create-linting-configuration-file-manually)
- [Contact](#contact)

<!-- Project Initialize -->
## Project Initialize

To start with the setup first you have to create new React App.
run this in the terminal
```
npx create-react-app my-app
cd my-app
```

<!-- Editor Setup -->

## Editor Setup

You can use any editor but as I personally prefer VS Code. I will give some instructions about how I prefer VS code to be setup for React applications.

### Plugins

You need to install the below plugins:

- ESLint by Dirk Baeumer
- Prettier - Code formatter by Prettier
- Dracula Official Theme (optional)

### Settings

Follow the below settings for VS Code -

1. Create a new folder called ".vscode" inside the project root folder
2. Create a new file called "settings.json" inside that folder.
3. Paste the below json in the newly created settings.json file and save the file.

```json
{
  // Theme
  "workbench.colorTheme": "Dracula",

  // config related to code formatting
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true,
  "[javascript]": {
    "editor.formatOnSave": false,
    "editor.defaultFormatter": null
  },
  "[javascriptreact]": {
    "editor.formatOnSave": false,
    "editor.defaultFormatter": null
  },
  "javascript.validate.enable": false, //disable all built-in syntax checking
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true,
    "source.fixAll.tslint": true,
    "source.organizeImports": true
  },
  "eslint.alwaysShowStatus": true,
  // emmet
  "emmet.triggerExpansionOnTab": true,
  "emmet.includeLanguages": {
    "javascript": "javascriptreact"
  }
}
```


## Linting Setup

In order to lint and format your React project automatically according to popular airbnb style guide, I recommend you to follow the instructions below.

### Install Dev Dependencies

Copy these dev dependencies and past package.json file. And then run in the terminal 

```
npm install
```


```json
"devDependencies": {
	"@babel/eslint-parser": "^7.5.4",
	"eslint":"^7.28.0",
	"eslint-config-airbnb": "18.2.1",
	"eslint-config-prettier":"^8.0.0",
	"eslint-plugin-import": "^2.22.1",
	"eslint-plugin-jsx-a11y":"^6.4.1",
	"eslint-plugin-prettier":"^3.3.1",
	"eslint-plugin-react":"^7.21.5",
	"eslint-plugin-react-hooks":"^4.0.0",
	"prettier":"^2.2.1"
}
```

and then simply run the below command in the terminal -

```sh
npm install
```

### Create Linting Configuration file manually

Create a `.eslintrc` file in the project root and enter the below contents:

```json
{
"extends": [
"airbnb",
"airbnb/hooks",
"eslint:recommended",
"prettier",
"plugin:jsx-a11y/recommended"
],
"parser":  "@babel/eslint-parser",
"parserOptions": {
"babelOptions": {
"presets": ["@babel/preset-react"]
},
"ecmaVersion":  8,
"requireConfigFile":  false
},
"env": {
"browser":  true,
"node":  true,
"es6":  true,
"jest":  true
},
"rules": {
"react/react-in-jsx-scope":  0,
"react-hooks/rules-of-hooks":  "error",
"no-console":  0,
"react/state-in-constructor":  0,
"indent":  0,
"linebreak-style":  0,
"react/prop-types":  0,
"jsx-a11y/click-events-have-key-events":  0,
"react/jsx-filename-extension": [
1,
{
"extensions": [".js", ".jsx"]
}
],
"prettier/prettier": [
"error",
{
"trailingComma":  "es5",
"singleQuote":  true,
"printWidth":  100,
"tabWidth":  4,
"semi":  true,
"endOfLine":  "auto"
}
]
},
"plugins": ["prettier", "react", "react-hooks"]
}
```