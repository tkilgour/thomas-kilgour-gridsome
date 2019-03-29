---
title: Setting Up A Gridsome Project With Tailwind CSS
date: 2019-03-29T12:51:49.776-0400
slug: setting-up-a-gridsome-project-with-tailwind-css
---

Setting up your [Gridsome](https://gridsome.org/) project with [Tailwind CSS](https://tailwindcss.com) is extremely simple, thanks to [gridsome-plugin-tailwindcss](https://gridsome.org/plugins/gridsome-plugin-tailwindcss).

Make sure you've set up your Gridsome project by following the [excellent documentation](https://gridsome.org/docs/).

## Setting up the plugin

Install the plugin as a dev dependency. No need to install Tailwind CSS separately, it's comes along as a dependency:

`npm install gridsome-plugin-tailwindcss --save-dev`

Then add it to the plugins section of your config file:

```js
// ./gridsome.config.js

plugins: [
  {
    use: 'gridsome-plugin-tailwindcss'
  }
]
```

By default, it will look for `tailwind.js` at the root of your project, but you can also specify a custom file path:

```js
// ./gridsome.config.js

plugins: [
  {
    use: 'gridsome-plugin-tailwindcss',
    options: {
      config: './path/to/config.js'
    }
  }
]
```

## Generate the Tailwind config file

Create a new `tailwind.js` file at the root of your project:

`npx tailwind init`

## Inject Tailwind into CSS

The last step to get Tailwind up and runnning is to inject it into your CSS using the `@tailwind` directive. An simple way to do this is to add it to th `<style>` tag of your default layout:

```
// ./src/layouts/Default.vue

<style>
@tailwind preflight;

@tailwind components;

@tailwind utilities;
</style>
```

That's it! You should now be able to start adding Tailwind classes throughout your Gridsome application.