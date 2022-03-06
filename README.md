# Set up ESLint + Prettier for React and Testing Library / Jest VS Code


#### Prerequisites

A react project created with with [Create React App](https://github.com/facebook/create-react-app).
```
~$ npm create-react-app myapp
```

#### Setup ESLint

Install plugins for Testing Library and Jest

```
~$ cd myapp
~/myapp/$ npm install eslint-plugin-testing-library eslint-plugin-jest-dom
```

Remove the `eslintConfig` block from `package.json`
```
 "eslintConfig": {
    "extends": [
      "react-app",
      "react-app/jest"
    ]
  },
```

If not already available, create a `.eslintrc.json` in the project root and make sure it contains the following:
```
{
  "env": {
    "browser": true,
    "es2021": true
  },
  "extends": [
    "react-app",
    "react-app/jest",
    "plugin:react/recommended",
    "plugin:testing-library/react",
    "plugin:jest-dom/recommended"
  ],
  "parserOptions": {
    "ecmaFeatures": {
      "jsx": true
    },
    "ecmaVersion": "latest",
    "sourceType": "module"
  },
  "plugins": ["react", "testing-library", "jest-dom"],
  "rules": {}
}
```
Install the ESLint extension in VS Code (https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)


Create a `.vscode/settings.json` file with the following content:

```
{
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  }
}
```
Add `.vscode` to `.gitignore`

#### Setup Prettier

Add defaultFormatter and formatOnSave settings to `.vscode/settings.json`:

```
{
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true
}
```
Optional:

Create a `.prettierrc.json` file with following
```
{
  "trailingComma": "es5",
  "tabWidth": 4,
  "semi": false,
  "singleQuote": true
}
``` 

