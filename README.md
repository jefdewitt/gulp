# gulp
This is a simple repo for managing my gulpfile. This specific gulpfile is for a Jekyll site, which requires some non-standard workarounds. Also, just to raise the level of difficulty, an AngularJS app is nested inside the Jekyll site. Therefore, there are a couple of concat and uglification tasks instead of just one.

The dependencies I used were:
  **browser-sync**
  - testing site/app across multipled devices simultaneously and auto-refresh on css file changes.
  
  **childprocess**
  - Module to support Multiple Process Code Coverage with istanbul. I don't really know what that is but I use to serve up        the Jekyll site in leu of the Terminal command `jekyll serve` that is commmonly used for local Jekyll development.
  
  **gulp-concat**
  - Concatenates multiple files together into a single source.
  
  **gulp-uglify**
  - Minifies JavaScript files, removing white space, decreasing file size.
  
  **gulp-rename**
  - Allows for files to be renamed during tasks.
  
  **gulp-sass**
  - Gulp Sass compilation into CSS.
  
  **gulp-sourcemaps**
  - Creates sourcemaps for identifying specific file locations for style rules and JavaScript.
     
  **gulp-clean-css**
  - Minfies CSS files.
     
  **del**
  - Removes files during tasks.
    
Explain the ins-and-outs about the parts of the compiling task.

Explain the ins-and-outs about the parts of the minifying task.

Explain why minifying won't work with mapping css.
    
Explain the custom Jekyll Serve Task

Explain the watch method

Explain the default task
