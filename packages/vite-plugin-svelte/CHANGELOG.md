# @sveltejs/vite-plugin-svelte

## 1.0.0-next.12

### Minor Changes

- [#75](https://github.com/sveltejs/vite-plugin-svelte/pull/75) [`f6f56fe`](https://github.com/sveltejs/vite-plugin-svelte/commit/f6f56fee7d3567196052a23440cb1818187fa232) Thanks [@dominikg](https://github.com/dominikg)! - resolve svelte to svelte/ssr when building for ssr (see #74)

* [#78](https://github.com/sveltejs/vite-plugin-svelte/pull/78) [`2eb09cf`](https://github.com/sveltejs/vite-plugin-svelte/commit/2eb09cf180c7ebf0fb4ccfccee663e5264b3814c) Thanks [@bluwy](https://github.com/bluwy)! - Support svg extension

- [#72](https://github.com/sveltejs/vite-plugin-svelte/pull/72) [`5100376`](https://github.com/sveltejs/vite-plugin-svelte/commit/5100376ef91d5e39ec00222f1043e4fda047678b) Thanks [@dominikg](https://github.com/dominikg)! - - Restart dev server when svelte config file changes
  - Refactored e2e-tests to use package.json scripts
  - Updated dependencies

* [#68](https://github.com/sveltejs/vite-plugin-svelte/pull/68) [`9583900`](https://github.com/sveltejs/vite-plugin-svelte/commit/9583900a2b3600133cee3a46b6dbb7df137977b6) Thanks [@dominikg](https://github.com/dominikg)! - feat: Allow svelte imports to be added to optimizeDeps.include and don't exclude svelte from optimizeDeps then

- [#64](https://github.com/sveltejs/vite-plugin-svelte/pull/64) [`c3f65fd`](https://github.com/sveltejs/vite-plugin-svelte/commit/c3f65fdf414b22810ad60817b3e1e62790ba816f) Thanks [@dominikg](https://github.com/dominikg)! - feat: vite config can be updated based on values in svelte config, provide knownJsSrcExtensions (see #60)

### Patch Changes

- [#70](https://github.com/sveltejs/vite-plugin-svelte/pull/70) [`377d464`](https://github.com/sveltejs/vite-plugin-svelte/commit/377d464eba30c56f012deba3d306cb5a7195b787) Thanks [@benmccann](https://github.com/benmccann)! - relax svelte peer dependency to 3.34.0

* [#55](https://github.com/sveltejs/vite-plugin-svelte/pull/55) [`09b63d3`](https://github.com/sveltejs/vite-plugin-svelte/commit/09b63d32e8816acc554a66d4d01062be197dfbb7) Thanks [@dominikg](https://github.com/dominikg)! - fix kit-node tests

- [#71](https://github.com/sveltejs/vite-plugin-svelte/pull/71) [`97ee68c`](https://github.com/sveltejs/vite-plugin-svelte/commit/97ee68c5106e58b2e7c4eb97e8cf7dd1c52bbfd3) Thanks [@dominikg](https://github.com/dominikg)! - output sourcemap in hmr helper preprocessor

* [#83](https://github.com/sveltejs/vite-plugin-svelte/pull/83) [`eb048ff`](https://github.com/sveltejs/vite-plugin-svelte/commit/eb048ff9419488f75869ffb880a78a2a3aa5a6bb) Thanks [@dominikg](https://github.com/dominikg)! - reduced debug output

## 1.0.0-next.11

### Major Changes

- [#54](https://github.com/sveltejs/vite-plugin-svelte/pull/54) [`0f7e256`](https://github.com/sveltejs/vite-plugin-svelte/commit/0f7e256a9ebb0ee9ac6075146d27bf4f11ecdab3) feat: convert to es module with cjs fallback, use named export instead of default

  If you are using vite-plugin-svelte with require, you should switch to esm and import the named export "svelte".
  An example can be found in the usage section of the [readme](README.md)

  For existing esm configs update your import to use the new named export.

  ```diff
  - import svelte from '@sveltejs/vite-plugin-svelte';
  + import { svelte } from '@sveltejs/vite-plugin-svelte';
  ```

  continuing with cjs/require is discouraged but if you must use it, update your require statement to use the named export

  ```diff
  - const svelte = require('@sveltejs/vite-plugin-svelte');
  + const { svelte } = require('@sveltejs/vite-plugin-svelte');
  ```

### Minor Changes

- [#45](https://github.com/sveltejs/vite-plugin-svelte/pull/45) [`673cf61`](https://github.com/sveltejs/vite-plugin-svelte/commit/673cf61b3800e7a64be2b73a7273909da95729d2) Feature: log svelte compiler warnings to console. use options.onwarn to customize logging

### Patch Changes

- [#44](https://github.com/sveltejs/vite-plugin-svelte/pull/44) [`24ae093`](https://github.com/sveltejs/vite-plugin-svelte/commit/24ae0934301cb50506bf39cdccc07ad3eac546fd) update to esbuild 0.12 and vite 2.3.7

* [#44](https://github.com/sveltejs/vite-plugin-svelte/pull/44) [`24ae093`](https://github.com/sveltejs/vite-plugin-svelte/commit/24ae0934301cb50506bf39cdccc07ad3eac546fd) update engines.node to "^12.20 || ^14.13.1 || >= 16"

- [#45](https://github.com/sveltejs/vite-plugin-svelte/pull/45) [`673cf61`](https://github.com/sveltejs/vite-plugin-svelte/commit/673cf61b3800e7a64be2b73a7273909da95729d2) enable logging for compiler warnings

## 1.0.0-next.10

### Minor Changes

- [#41](https://github.com/sveltejs/vite-plugin-svelte/pull/41) [`cb7f03d`](https://github.com/sveltejs/vite-plugin-svelte/commit/cb7f03d61c19f0b98c6412c11bbaa4af978da9ed) Feature: Allow `emitCss: false` for production builds and customizable compilerOptions.css and hydratable - fixes #9

## 1.0.0-next.9

### Patch Changes

- [#38](https://github.com/sveltejs/vite-plugin-svelte/pull/38) [`5aef91c`](https://github.com/sveltejs/vite-plugin-svelte/commit/5aef91c8752c8de94a1f1fcb28618606b7c44670) fix: ensure esm config loading works on windows

## 1.0.0-next.8

### Minor Changes

- [#35](https://github.com/sveltejs/vite-plugin-svelte/pull/35) [`4018ce6`](https://github.com/sveltejs/vite-plugin-svelte/commit/4018ce621b4df75877e0e18057c332f27158d42b) Feature: Support esm in svelte.config.js and svelte.config.mjs

* [#35](https://github.com/sveltejs/vite-plugin-svelte/pull/35) [`4018ce6`](https://github.com/sveltejs/vite-plugin-svelte/commit/4018ce621b4df75877e0e18057c332f27158d42b) Feature: add configFile option

### Patch Changes

- [#34](https://github.com/sveltejs/vite-plugin-svelte/pull/34) [`e5d4749`](https://github.com/sveltejs/vite-plugin-svelte/commit/e5d4749c0850260a295daab9cb15866fe58ee709) fix: watch preprocessor dependencies and trigger hmr on change

## 1.0.0-next.7

### Minor Changes

- [#32](https://github.com/sveltejs/vite-plugin-svelte/pull/32) [`113bb7d`](https://github.com/sveltejs/vite-plugin-svelte/commit/113bb7dc330a7517085d12d1d0758a376a12253f) Reduced cache usage, share css cache between SSR and client

## 1.0.0-next.6

### Minor Changes

- 1be46f1: improved css hmr
- a0f5a65: Allow other vite plugins to define preprocessors

### Patch Changes

- 8d9ef96: fix: do not preserve types unless useVitePreprocess option is true
- 6f4a253: disable svelte-hmr overlay by default
- 18647aa: improve virtual css module path (fixes #14)

## 1.0.0-next.5

### Patch Changes

- 61439ae: initial release
