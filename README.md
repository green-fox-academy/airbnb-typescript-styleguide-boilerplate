# How to automatically apply AirBnB style guide to your TypeScript project

This repo helps you to setup your environment for applying AirBnB TypeScript style guide with Visual Studio Code

- go to your project's root folder and run `npm init -y` if no `package.json` exists in your project's root folder
- run
```shell script
npm install --save-dev typescript @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint eslint-config-airbnb-base eslint-config-prettier eslint-import-resolver-typescript eslint-plugin-import eslint-plugin-json eslint-plugin-prettier prettier
```
- copy [.eslintrc.js](.eslintrc.js) from this repository to your project's root folder
- Add the following to your `package.json`
```text
"scripts": {
  "lint": "eslint . --ext .ts"
}
```

- Install the following Visual Studio Code extensions
```text
dbaeumer.vscode-eslint
esbenp.prettier-vscode
```

## How to edit your settings

Your VS Code settings are conveniently stored in a JSON file called `settings.json`.
To edit your settings in `settings.json`,
start by opening the Command Palette with CMD/CTRL + SHIFT + P.

From the Command Palette, you have a choice between at least two commands that edit your settings:
- The Open Settings (JSON) command will let you directly edit the settings JSON file.
- The Open Settings (UI) command will open a user-friendly UI to edit the settings JSON file indirectly.

Both options work equally well and present the same options.
Once you're in the settings tab, you can edit either user or workspace settings.
User settings apply globally for any VS Code instance,
while workspace settings only apply to the workspace you are currently working in.
Workspace settings override user settings.

- Add the following to your Visual Studio Code `settings.json`
```text
"[typescript]": {
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true
},
"editor.codeActionsOnSave": {
  "source.fixAll": true
},
"eslint.validate": [
  "typescript"
]
```

And that’s it! 
You should now have complete Visual Studio Code integration.
When you violate a linting rule, you’ll be visually alerted, and when you save a file,
ESLint will attempt to fix any issues using Prettier.

If you want to customize the VSCode Prettier plugin better,
then you can reach the documentation [here](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)

## Source

More detailed [article](https://levelup.gitconnected.com/setting-up-eslint-with-prettier-typescript-and-visual-studio-code-d113bbec9857)
extended with JS and React.

## Contribution

Feel free to fork and create pull requests. Keep in mind, this repo is only for basic TypeScript projects
without any framework.
