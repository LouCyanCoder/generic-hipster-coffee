Step 2 : Install
node_modules

We need to install the node_modules.

Luckily we have a ready-made package.json file that contains information about all the packages that need to be installed.

Therefore we don't need to install them one by one.

Instead, just run:

npm install

---------------------------------------------------------

What this ready-made gulpfile can do?

This gulpfile.js exports these tasks:

    structure - creates a basic src folder structure only so that you know where to put which files
    publish - copies all HTML files, fonts and images from their location in src into respective folders in dist
    build - builds the project once for production
    build_dev - builds the project once for development
    watch - builds the project for development, serves the contents of the dist folder with browsersync and starts watching the files in src so that when any of them change, dist gets rebuilt.

Compiling SCSS

The compileScss function which is present in all the build tasks compiles SCSS files from /src/scss and creates from them CSS files in /dist/css

When linking an HTML document to a CSS file, we must think about where it will appear in the dist folder after it has been compiled, not where it is now in src.

Therefore the proper relative URL of any file in /src/scss is not /scss but /css and the proper extension is .css, e.g. /css/style.css