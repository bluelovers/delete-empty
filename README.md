# delete-empty [![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=W8YFZ425KND68) [![NPM version](https://img.shields.io/npm/v/delete-empty.svg?style=flat)](https://www.npmjs.com/package/delete-empty) [![NPM monthly downloads](https://img.shields.io/npm/dm/delete-empty.svg?style=flat)](https://npmjs.org/package/delete-empty) [![NPM total downloads](https://img.shields.io/npm/dt/delete-empty.svg?style=flat)](https://npmjs.org/package/delete-empty) [![Linux Build Status](https://img.shields.io/travis/jonschlinkert/delete-empty.svg?style=flat&label=Travis)](https://travis-ci.org/jonschlinkert/delete-empty)

> Recursively delete all empty folders in a directory and child directories.

Please consider following this project's author, [Jon Schlinkert](https://github.com/jonschlinkert), and consider starring the project to show your :heart: and support.

- [Install](#install)
- [Usage](#usage)
- [API](#api)
  * [async-await (promise)](#async-await-promise)
  * [async callback](#async-callback)
  * [sync](#sync)
- [CLI](#cli)
- [About](#about)

_(TOC generated by [verb](https://github.com/verbose/verb) using [markdown-toc](https://github.com/jonschlinkert/markdown-toc))_

## Install

Install with [npm](https://www.npmjs.com/):

```sh
$ npm install --save delete-empty
```

## Usage

```js
const deleteEmpty = require('delete-empty');
```

## API

Given the following directory structure, the **highlighted directories** would be deleted.

```diff
foo/
└─┬ a/
-  ├── aa/
  ├── bb/
  │ └─┬ bbb/
  │ │ ├── one.txt
  │ │ └── two.txt
-  ├── cc/
-  ├ b/
-  └ c/
```

### async-await (promise)

If no callback is passed, a promise is returned. Returns the array of deleted directories.

```js
(async () => {
  let deleted = await deleteEmpty('foo');
  console.log(deleted); //=> ['foo/aa/', 'foo/a/cc/', 'foo/b/', 'foo/c/']
})();

// or
deleteEmpty('foo/')
  .then(deleted => console.log(deleted)) //=> ['foo/aa/', 'foo/a/cc/', 'foo/b/', 'foo/c/']
  .catch(console.error);
```

### async callback

Returns the array of deleted directories in the callback.

```js
deleteEmpty('foo/', (err, deleted) => {
  console.log(deleted); //=> ['foo/aa/', 'foo/a/cc/', 'foo/b/', 'foo/c/']
});
```

### sync

Returns the array of deleted directories.

```js
console.log(deleteEmpty.sync('foo/')); //=> ['foo/aa/', 'foo/a/cc/', 'foo/b/', 'foo/c/']
```

## CLI

To use the `delete-empty` command from any directory you must first install the package globally with the following command:

```sh
$ npm install --global delete-empty
```

**Usage**

```
Usage: $ delete-empty <directory> [options]

Directory: (optional) Initial directory to begin the search for empty
           directories. Otherwise, cwd is used.

[Options]:
  -c, --cwd           Set the current working directory for folders to search.
  -d, --dryRun        Do a dry run without deleting any files.
  -h, --help          Display this help menu
  -V, --version       Display the current version of rename
  -v, --verbose       Display all verbose logging messages (currently not used)

```

## About

<details>
<summary><strong>Contributing</strong></summary>

Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](../../issues/new).

</details>

<details>
<summary><strong>Running Tests</strong></summary>

Running and reviewing unit tests is a great way to get familiarized with a library and its API. You can install dependencies and run tests with the following command:

```sh
$ npm install && npm test
```

</details>

<details>
<summary><strong>Building docs</strong></summary>

_(This project's readme.md is generated by [verb](https://github.com/verbose/verb-generate-readme), please don't edit the readme directly. Any changes to the readme must be made in the [.verb.md](.verb.md) readme template.)_

To generate the readme, run the following command:

```sh
$ npm install -g verbose/verb#dev verb-generate-readme && verb
```

</details>

### Related projects

You might also be interested in these projects:

* [copy](https://www.npmjs.com/package/copy): Copy files or directories using globs. | [homepage](https://github.com/jonschlinkert/copy "Copy files or directories using globs.")
* [delete](https://www.npmjs.com/package/delete): Delete files and folders and any intermediate directories if they exist (sync and async). | [homepage](https://github.com/jonschlinkert/delete "Delete files and folders and any intermediate directories if they exist (sync and async).")
* [fs-utils](https://www.npmjs.com/package/fs-utils): fs extras and utilities to extend the node.js file system module. Used in Assemble and… [more](https://github.com/assemble/fs-utils) | [homepage](https://github.com/assemble/fs-utils "fs extras and utilities to extend the node.js file system module. Used in Assemble and many other projects.")
* [matched](https://www.npmjs.com/package/matched): Adds array support to node-glob, sync and async. Also supports tilde expansion (user home) and… [more](https://github.com/jonschlinkert/matched) | [homepage](https://github.com/jonschlinkert/matched "Adds array support to node-glob, sync and async. Also supports tilde expansion (user home) and resolving to global npm modules.")

### Contributors

| **Commits** | **Contributor** |  
| --- | --- |  
| 31 | [jonschlinkert](https://github.com/jonschlinkert) |  
| 2  | [treble-snake](https://github.com/treble-snake) |  
| 1  | [doowb](https://github.com/doowb) |  
| 1  | [svenschoenung](https://github.com/svenschoenung) |  
| 1  | [vpalmisano](https://github.com/vpalmisano) |  

### Author

**Jon Schlinkert**

* [GitHub Profile](https://github.com/jonschlinkert)
* [Twitter Profile](https://twitter.com/jonschlinkert)
* [LinkedIn Profile](https://linkedin.com/in/jonschlinkert)

### License

Copyright © 2019, [Jon Schlinkert](https://github.com/jonschlinkert).
Released under the [MIT License](LICENSE).

***

_This file was generated by [verb-generate-readme](https://github.com/verbose/verb-generate-readme), v0.8.0, on July 02, 2019._