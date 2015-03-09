# The Mozaik WordPress Theme Boilerplate

The goals of the boilerplate are to:

1. be a product used and produced by the entire team (suggestions, issues and pull requests are welcome and encouraged)
1. be easy to set up
1. be easy to use
1. be easy to understand
1. be easy to extend/modify
1. guide the development process to be consistent where it can be
1. offer a robust development and build workflow (currently powered by the cli and gulp)
1. make getting off the ground with a new project really fast

## Reading Recommendations

1. [WordPress Developer Documentation](http://codex.wordpress.org/Developer_Documentation)
1. We generally follow the [WordPress PHP Coding Standards](https://make.wordpress.org/core/handbook/coding-standards/php/) in our WP code
1. This project uses [webpack](http://webpack.github.io/) to provide support for modular JS, read up on the functionality & tools it provides

## Important Prerequisites

### Technical

1. Have [node and npm](https://nodejs.org/) installed on your system
1. Have [gulp](https://github.com/gulpjs/gulp/blob/master/docs/getting-started.md) globally installed

### WordPress

1. Read [the WordPress theme development guidelines](http://codex.wordpress.org/Theme_Development)
1. Understand [the WordPress template hierarchy](http://codex.wordpress.org/images/9/96/wp-template-hierarchy.jpg)
1. Understand [the WordPress Loop](http://codex.wordpress.org/The_Loop)
1. Understand [how WordPress helps with Data Validation/Sanitization](http://codex.wordpress.org/Data_Validation)
1. Read up on the following WordPress core APIs:
	- [the Plugin API](http://codex.wordpress.org/Plugin_API)
	- [the Shortcode API](http://codex.wordpress.org/Shortcode_API)
	
### JavaScript

1. Understand [modular JavaScript](http://addyosmani.com/writing-modular-js/)

## Development Guidelines

- Avoid committing the built theme to the project repository
- Avoid committing the `wp-uploads` directory to the project repository
- Avoid making changes directly to the built theme -- Always use the build process
- In production avoid uploading the theme development directory to a public server
- It is good practice to enable `WP_DEBUG` in your `wp-config.php` file, *but only* during development

## Standard Theme Development Process

### Setup

1. Install WordPress and clear it of unnecessary default themes & plugins
1. Clone/Download this repository into a directory in your WordPress `wp-content/themes` directory
1. Open the terminal and `cd wp-content/themes/<devthemename>`
1. Run `npm install` to install all dev dependencies
1. Change the `package.json` with your new theme's configuration
1. Run `gulp` to begin the dev build process that uses libsass, browser-sync and webpack
1. Log in to the admin and enable the *built theme*

### Development

1. Run `gulp` to begin the dev build process that uses libsass, browser-sync and webpack
1. Develop your theme in the `/assets` and `/theme` directories, the built theme will be generated by gulp
1. For your convenience during development:
	- use `npm install --save <module(s)>` to easily manage dependencies, then use `var <module> = require('<module>');` anywhere you want to use them
	- explore the `/library` directory in the dev theme for anything useful to your project. If you find anything
	  copy it into your `/theme` folder somewhere under `/theme/includes`, modify it as you require and include it where you need it <== Not implemented yet

### Production

1. Delete files you are not using from inside the `/theme` directory
1. [Add a screenshot.png](http://codex.wordpress.org/Theme_Development#Screenshot)
1. Before deploying run `gulp --build` to generate a production ready version of the built theme
1. Deploy the built theme directory, *not the dev directory*