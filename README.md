# 🌙 nightenv [![npm](https://img.shields.io/npm/dt/nightenv.svg)](https://github.com/tomselvi/nightenv#installation)

`nightenv` can be configured to change your editor themes, OS themes, and more based on the time of day.

## Table of Contents

* [Requirements](#requirements)
* [Installation](#installation)
* [Usage](#usage)
* [nightenv plugins](#nightenv-plugins)
  * [Terminals](#terminals)
  * [Editors/IDEs](#editorsides)
  * [OS](#os)
* [About](#about)
* [Roadmap](#roadmap)

## Requirements

* node >= 6.11

## Installation

```sh
npm i -g nightenv
nightenv
```

`nightenv` can be run multiple times without side effects.  To uninstall, find the entry in your crontab via `crontab -e` and remove it, followed by `npm rm -g nightenv`.

## Usage

`nightenv` can be configured via `~/.nightenv.json`.  Add a new entry based on sample configuration provided by your plugins.

## nightenv plugins

### Terminals

* [nightenv-iterm](https://github.com/tomselvi/nightenv/tree/master/packages/nightenv-iterm)

### Editors/IDEs

* [nightenv-vscode](https://github.com/tomselvi/nightenv/tree/master/packages/nightenv-vscode)

### Productivity

* [nightenv-slack](https://github.com/tomselvi/nightenv/tree/master/packages/nightenv-slack)

### OS

* [nightenv-osx](https://github.com/tomselvi/nightenv/tree/master/packages/nightenv-osx)

### Create your own plugin

To create your own plugin, create a JavaScript file that exports a `execute` function, like so:

```js
module.exports.execute = function(config, isNight) {

  // config is an object that contains configuration arbitrarily
  // defined by your plugin

  // isNight is a boolean that represents whether it is night time

  // this function should return a promise with the configuration
  // containing any updates if there are any, giving your plugin
  // the ability to maintain state

};
```

## About

After many days of switching between dark and light themes to reduce eye strain, I needed an automated solution, hence `nightenv`.  This is not meant to be a state of the art piece of software, but instead it was meant to be a quick and easy tool that could be easily extended.  Feel free to contribute new plugins or update the already existing ones if you have any issues.

Credits to [themer](https://github.com/mjswensen/themer) and [mjswensen](https://github.com/mjswensen) for the inspiration to whip this together.

## Roadmap

Will probably declare v1 after the following items are compeleted, not in any particular order:

* tests / coverage
* tmux
* vim
* slack
* Windows 10
* Linux
* ?
