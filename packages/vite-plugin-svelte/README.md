# @sveltejs/vite-plugin-svelte

## usage

```js
import { svelte } from '@sveltejs/vite-plugin-svelte';
import { defineConfig } from 'vite';

export default defineConfig(({ command, mode }) => {
	const isProduction = mode === 'production';
	return {
		plugins: [
			svelte({
				/* inline options here */
			})
		],
		build: {
			minify: isProduction
		}
	};
});
```

### commonjs

If you cannot use import and need commonjs, vite-plugin-svelte provides a fallback build in `dist/index.cjs`

require it like this:

```js
const { svelte } = require('@sveltejs/vite-plugin-svelte');
```

## Options

vite-plugin-svelte reads the vite configuration and uses an appropriate default configuration

It also loads `svelte.config.js` (or `svelte.config.cjs`) from the configured `vite.root` directory automatically.

Options are merged in the following order:

1. vite-plugin-svelte defaults
2. svelte.config.js in vite.root
3. inline options passed in vite.config.js

It supports all options from rollup-plugin-svelte and some additional options to tailor the plugin to your needs.

For more Information check [options.ts](src/utils/options.ts)

## Importing third-party Svelte libraries

When importing any third-party libraries that uses Svelte's lifecycle API, e.g. `onMount`, `setContext`, and others, they need to be excluded from Vite's dependency pre-bundling process:

<!-- eslint-skip -->

```js
// vite.config.js
{
	plugins: [svelte()],
	optimizeDeps: {
		exclude: ['svelte-library']
	}
}
```

This is needed because [Vite's dependency pre-bundling doesn't deduplicate the Svelte instance](https://github.com/vitejs/vite/issues/3910), resulting in multiple Svelte instance running at once, causing errors like `Function called outside component initialization`.

If you're unsure whether a library uses the lifecycle API, place it in `optimizeDeps.exclude` and you'll be fine. The team is working on removing this limitation soon.

## Integrations for other vite plugins

### Add an extra preprocessor

vite-plugin-svelte uses the svelte compiler to split `.svelte` files into js and css and the svelte compiler requires that the css passed to it is already plain css.
If you are building a plugin for vite that transforms css and want it to work out of the box with vite-plugin-svelte, you can add a `sveltePreprocess: PreprocessorGroup` to your vite plugin definition and vite-plugin-svelte will pick it up and add it to the list of svelte preprocessors used at runtime.

```js
const vitePluginCoolCss = {
	name: 'vite-plugin-coolcss',
	sveltePreprocess: {
		/* your PreprocessorGroup here */
	}
	/*... your cool css plugin implementation here .. */
};
```

Check out [windicss](https://github.com/windicss/vite-plugin-windicss/blob/517eca0cebc879d931c6578a08accadfb112157c/packages/vite-plugin-windicss/src/index.ts#L167)

## License

MIT
