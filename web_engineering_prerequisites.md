# Web-Workshop: Prerequisites

> Author: [mario.ranftl@allaboutapps.at](https://confluence.allaboutapps.at/mailto:/mario.ranftl@allaboutapps.at)
>

Please install the following tools and the sample frontend project in preparation to our workshop from.

### General Setup

Install the following tools:

* [git](https://git-scm.com/): Version control
* [Chrome](https://www.google.de/chrome/browser/desktop/index.html) + [React Developer Tools](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi): Web-App Development Environment
* [Visual Studio Code](https://code.visualstudio.com/): *"VS Code"* - Your IDE for developing with [TypeScript](https://www.typescriptlang.org/)
* *(optional)* [Typora](https://typora.io/): A sane Editor for Markdown `.md` files
* *(optional)* [Sourcetree](https://www.sourcetreeapp.com/): A sane way to work with git branches without using the command line

### Node.js Setup

We are going to use `nvm` to manage different [Node.js](https://nodejs.org/en/) / [npm](https://www.npmjs.com/) versions running on the same computer. 

#### nvm (Win)

> [nvm-windows](https://github.com/coreybutler/nvm-windows): A node.js version management utility for Windows.

- Download and install [Release 1.15](https://github.com/coreybutler/nvm-windows/releases/download/1.1.5/nvm-setup.zip) (not the prerelease 1.16).
- `nvm` was now installed and added to your `PATH`, launch a new `cmd` session...

#### nvm (MacOS, Linux)

> [nvm](https://github.com/creationix/nvm): Node Version Manager - Simple bash script to manage multiple active node.js versions

- Install `nvm` as specified on [here](https://github.com/creationix/nvm#install-script)
- `nvm` was now installed and added to your `PATH`, launch a new `bash`/`zsh` session...

#### Node.js installation (Win, MacOS, Linux)

In your preferred shell, do the following:

```bash
# Check if installation of nvm has worked as expected...
nvm version
# 1.1.5 (windows) or v0.33.x (macOS, linux)

# Check for already installed Node.js versions
nvm list
# No installations recognized.

# Install Node.js (the current LTS version)
nvm install v6.11.4
# Node.js and npm are now installed!

# Setup your ENV to use the just installed version by default
nvm use 6.11.4

# node and npm in their respective versions are now in your PATH (in all shells)!
# Recheck if everything works (outputs version of node and npm)
node -v
npm -v
```

### Web-Frontend Project Setup

We are going to install the following packages **globally** (these are not an application dependencies) on our system:

* [yarn](https://yarnpkg.com/lang/en/): Fast, reliable, and secure dependency management. An alternative to npm.
* [create-react-app](https://github.com/facebookincubator/create-react-app): Create React apps with no build configuration. A project scaffolder.

Finally we'll use [aaa-create-react-app-typescript](https://github.com/majodev/aaa-create-react-app-typescript) to scaffold a new frontend application which encapsulates the [webpack](https://webpack.github.io/) build-pipeline and other recommendations (linting, project-structure, ...) from all about apps.

```bash
# Install yarn and create-react-app globally
npm install -g yarn create-react-app

# Setup a new aaa react frontend app through create-react-app
# The new app will be called "test-app" and will live in this very folder in your cwd
create-react-app test-app --scripts-version=aaa-react-scripts-ts

# Launch your newly installed app...
cd test-app
yarn start
```

Your newly scaffolded app should now be available at [localhost:3000](http://localhost:3000).

Feel free to open the `test-app` directory now with VS Code to mess around with it...

### VS Code Setup

* Install the recommended extensions for the project.
* *(optional)* At aaa we use the following default settings for VS Code (accessed via Code/File —> Settings —> Settings):

```json
{
    "editor.renderWhitespace": "boundary",
    "tslint.autoFixOnSave": true,
    "editor.formatOnSave": true,
    "editor.formatOnPaste": true,
    "editor.formatOnType": true,
    "files.associations": {
        "*.j2": "shellscript",
        "*.env": "shellscript"
    },
    "workbench.colorTheme": "Monokai",
    "workbench.iconTheme": "vs-seti",
    "editor.minimap.enabled": true,
    "editor.minimap.renderCharacters": false,
    "window.zoomLevel": 0,
    "search.useIgnoreFilesByDefault": true,
    "typescript.implementationsCodeLens.enabled": true,
    "extensions.ignoreRecommendations": false,
}
```

