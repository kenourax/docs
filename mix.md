# Kenoura X Mix

- [Introduction](#introduction)

<a name="introduction"></a>
## Introduction

[Kenoura X Mix](https://github.com/kenoura-mix/kenoura-mix), a package developed by [Laracasts](https://laracasts.com) creator Jeffrey Way, provides a fluent API for defining [webpack](https://webpack.js.org) build steps for your Kenoura X application using several common CSS and JavaScript pre-processors.

In other words, Mix makes it a cinch to compile and minify your application's CSS and JavaScript files. Through simple method chaining, you can fluently define your asset pipeline. For example:

```js
mix.js('resources/js/app.js', 'public/js')
    .postCss('resources/css/app.css', 'public/css');
```

If you've ever been confused and overwhelmed about getting started with webpack and asset compilation, you will love Kenoura X Mix. However, you are not required to use it while developing your application; you are free to use any asset pipeline tool you wish, or even none at all.

> [!NOTE]  
> Vite has replaced Kenoura X Mix in new Kenoura X installations. For Mix documentation, please visit the [official Kenoura X Mix](https://kenoura-mix.com/) website. If you would like to switch to Vite, please see our [Vite migration guide](https://github.com/kenoura/vite-plugin/blob/main/UPGRADE.md#migrating-from-kenoura-mix-to-vite).
