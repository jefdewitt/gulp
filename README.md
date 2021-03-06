# gulp
This is a simple repo for managing my gulpfile. This specific gulpfile is for a Jekyll site, so unconventional methods are used to work with `jekyll serve`. Also, just to raise the level of difficulty, an AngularJS app is nested inside the Jekyll site. Therefore, there are a couple of concat and uglification tasks instead of just one.

## Initial Setup

Have `node.js` & `npm` installed on your machine.

Run `npm install gulp -g` in Terminal.

Run `npm init` to create a package.json file, which we'll use to track dependencies.

Run `npm install gulp --save-dev` to install `gulp` as our first project dependency. Pay attention to the `--save-dev` flag. This adds dependencies to our `package.json` file. 

## Dependencies

**browser-sync** - testing site/app across multiple devices simultaneously and auto-refresh on css file changes.
  
**childprocess** - Module to support Multiple Process Code Coverage with istanbul. I don't really know what that is but I use to serve up the Jekyll site in lieu of the Terminal command `jekyll serve` that is commmonly used for local Jekyll development.
  
**gulp-concat** - Concatenates multiple files together into a single source.
  
**gulp-uglify** - Minifies JavaScript files, removing white space, decreasing file size.
  
**gulp-rename** - Allows for files to be renamed during tasks.
  
**gulp-sass** - Gulp Sass compilation into CSS.
  
**gulp-sourcemaps** - Creates sourcemaps for identifying specific file locations for style rules and JavaScript.
     
**gulp-clean-css** - Minifies CSS files.
     
**del** - Removes files during tasks.
    
## Tasks

The **watch** task uses the gulp `watch` method to identify changes made to files. It takes two arguments. The first is a string or an array of files to watch. The second argument is an array of tasks to perform. Put simply, when changes are saved in the file(s) of the first param the task(s) from the second param are fired off.

  - One note of interest, notice the 'globbing' patterns used in this task. These filepaths, denoted with multiple or single asterisks, simplify the selection of files by way of choosing entire directories and/or files that end in a specific extension type.
  
  `['_sass/**/*.scss', 'trackerkeeper/styles/scss/**/*.scss']`

The **clean** task makes use of the `del` module. The `del` module takes a string or an array of files/file paths (notice the `glob` pattern again) to delete, or `clean`. This prevents files created from previous gulp tasks being duplicated.

The `default` gulp task is what I'm using to tie it all together. It taks an array of other tasks as arguments to run. Just type `gulp` in the command line and wham-bam-thank-you-maam. 

## Odds & Ends

My tasks that use **gulp-uglify** and **gulp-clean-css** depend on concatenated files. Gulp runs tasks concurrently by default so as a means to run tasks in order we use a two-step process. The first step is adding the `concat` tasks as dependencies of the `minification` tasks. The second step is adding `return` keywords to the `concat` tasks. This tells the tasks that have dependencies to wait until the those dependencies are finished before they themselves run. 

**gulp-sourcemaps** will not work with minified files. The solution I've found for this is simply pointing CSS/JS `link` tags toward unminified files while in development. When it comes time to go live I change the source back to the `.min` versions.

Since Jekyll comes with a development server baked-in, it was tricky to get gulp to initiate it. The solution is one I found online and don't entirely understand. The `childprocess` module uses a `spawn` method and seems to take an object with a `{stdio: 'inherit'}` key-value pair as a parameter. I'm tired and that's as far as I feel like getting into it right now. It's weird.

