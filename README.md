# lerna-starter

<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
[![Travis Build Status](https://img.shields.io/travis/jedmao/lerna-starter.svg?branch=master&style=flat-square)](https://travis-ci.com/jedmao/lerna-starter)
[![codecov](https://img.shields.io/codecov/c/gh/jedmao/lerna-starter?style=flat-square)](https://codecov.io/gh/jedmao/lerna-starter)
[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg?style=flat-square)](http://commitizen.github.io/cz-cli/)
[![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg?style=flat-square)](https://github.com/prettier/prettier)
[![types: TypeScript](https://img.shields.io/npm/types/typescript?style=flat-square)](https://typescriptlang.org)
[![lerna](https://img.shields.io/badge/maintained%20with-lerna-cc00ff.svg?style=flat-square)](https://lerna.js.org/)
<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

Starter project for a [Lerna][]/[TypeScript][] monorepo.

## Features

- Manage multi-package [git][]/[npm][] repositories with [Lerna][].
- First-class [TypeScript][] support. Type definitions are generated and
  published for each package.
- [ESLint](https://eslint.org/), configured with
  [XO](https://github.com/xojs/xo) +
  [TypeScript](https://typescript-eslint.io/).
- Format code (and more) with [Prettier](https://prettier.io/).
- [Jest](https://jestjs.io/) testing framework, configured with
  [`ts-jest`](https://kulshekhar.github.io/ts-jest/) and 100% test coverage.
- Prevent bad commits/pushes with [Husky](https://www.npmjs.com/package/husky)
  commit hooks 🐶 _woof!_
- [Commitizen-friendly](https://github.com/commitizen/cz-cli#making-your-repo-commitizen-friendly)
  repo with [conventional commits](https://www.conventionalcommits.org/) and
  [generated CHANGELOG](https://github.com/conventional-changelog/conventional-changelog).
- Continuous integration with [Travis-CI](https://travis-ci.com/).

  - Enable automatic publishing to [npm][] by creating an
    [npm token](https://docs.npmjs.com/cli/token) and adding it as `NPM_TOKEN`
    to your
    [Travis environment variables](https://docs.travis-ci.com/user/environment-variables/).
  - Enable automatic [GitHub][] release commits by creating a
    [GitHub token](https://github.com/settings/tokens/new) with `public_repo`
    access and adding it as `GH_TOKEN` in Travis (see above).
  - Coverage reports uploaded to [Codecov](https://codecov.io/).
  - [Greenkeeper](https://greenkeeper.io/) enabled.

## Installation

This project is setup as a
[GitHub repository template](https://github.blog/2019-06-06-generate-new-repositories-with-repository-templates/),
but really is designed to use [Pollinate][] to generate a new project directly
from [GitHub][] using a simple [schema](#options).

```sh
$ npx pollinate https://github.com/jedmao/lerna-starter.git [options]
```

## Options

All options are optional. Imagine that!

Refer to [Pollinate][] docs for the various ways in which you can provide
options.

### author

Use the `Name <email> (url)` format, where `email` and `url` are optional. This
is for the
[`author` field in package.json](https://docs.npmjs.com/files/package.json#people-fields-author-contributors).

### name

Typically the name of the monorepo project, but falls back to the [`org`](#org)
if not provided.

See [org/name resolution](#org-name-resolution) for more information.

### org

If provided, must match a
[GitHub organization](https://github.com/settings/organizations) or username to
which you have access. If not provided, it falls back to the [`name`](#name).

See [org/name resolution](#option-resolution) for more information.

### description

Included in your core `package.json` and `README.md`.

## org/name resolution

Though optional, you must provide at least one of the following options:
[`org`](#org), [`name`](#name). They will be used in tandem to construct your
[GitHub path](#github-path) and [npm package name](#npm-package-name).

### [GitHub][] path

- `/{{ org or name }}/{{ name or org }}`

### [npm][] package name

- `@{{ name or org }}/core`

## This README will self destruct 💣

The moment you [pollinate][]. 🌺🐝

[git]: https://git-scm.com/
[github]: https://github.com/
[lerna]: https://lerna.js.org/
[npm]: https://www.npmjs.com/
[npm org]: https://www.npmjs.com/org/create
[pollinate]: https://www.npmjs.com/package/pollinate
[typescript]: https://www.typescriptlang.org/
