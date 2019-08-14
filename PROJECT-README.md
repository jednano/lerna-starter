# {{ name or org }}

<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
[![Travis Build Status](https://img.shields.io/travis/{{ org or name }}/{{ name or org }}.svg?branch=master&style=flat-square)](https://travis-ci.com/{{ org or name }}/{{ name or org }})
[![codecov](https://img.shields.io/codecov/c/gh/{{ org or name }}/{{ name or org }}?style=flat-square)](https://codecov.io/gh/{{ org or name }}/{{ name or org }})
[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg?style=flat-square)](http://commitizen.github.io/cz-cli/)
[![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg?style=flat-square)](https://github.com/prettier/prettier)
[![types: TypeScript](https://img.shields.io/npm/types/typescript?style=flat-square)](https://typescriptlang.org)
[![lerna](https://img.shields.io/badge/maintained%20with-lerna-cc00ff.svg?style=flat-square)](https://lerna.js.org/)
<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

{{ description }}

## Scripts

The following [npm scripts](https://docs.npmjs.com/misc/scripts) are made
available to you in the project root. You can run each of them with
`npm run <script-name>`.

If you want to limit the scope of a script to a particular package, add the
`--scope` option to the command (e.g.,
`npm run clean -- --scope=@{{ org or name }}/core`). See [run options][].

You can also run [Lerna commands](https://lerna.js.org/#commands) in this
project. It is recommended that you use
[`npx`](https://www.npmjs.com/package/npx) to run these commands (i.e.,
`npx lerna <command>`).

### clean

_Supports [run options][]._

Clean coverage results in `./coverage` and runs `npm run clean` for each
package.

### lint

_Supports [run options][]._

Runs ESLint for each package.

### check-types

_Supports [run options][]._

Runs the TypeScript compiler for each package without emitting any files. This
is used in a pre-push hook for a faster alternative than a full build, so you
probably won't want to run it directly.

### build

_Supports [run options][]._

Runs the TypeScript compiler for each package.

### test

Runs [Jest][] in [watch mode](https://jestjs.io/docs/en/cli.html#watch), which
attempts to run
[only on changed files](https://jestjs.io/docs/en/cli.html#onlychanged).

This command doesn't support `--scope`, but you can narrow the test run by
adding filename (path) filters in as many `...args` that follow (e.g.,
`npm test core/src`).

### cover

Runs [Jest][] in [coverage mode](https://jestjs.io/docs/en/cli.html#coverage),
dumping coverage results in `./coverage` and showing a text summary in the
console output.

Feel free to add more
[coverage reporters](https://jestjs.io/docs/en/configuration.html#coveragereporters-array-string)
to the list. The [Jest][] configuration can be found in the root `package.json`.

### commit

Runs [Commitizen](http://commitizen.github.io/cz-cli/) commit wizard, ensuring
that your commit messages conform to
[Conventional Commits](https://www.conventionalcommits.org/).

Use the [`git commit`](https://git-scm.com/docs/git-commit) command directly
with the
[`-n`, `--no-verify` option](https://git-scm.com/docs/git-commit#Documentation/git-commit.txt--n)
to bypasses the pre-commit and commit-msg hooks.

[jest]: https://jestjs.io/
[run options]: https://github.com/lerna/lerna/tree/master/commands/run#options
