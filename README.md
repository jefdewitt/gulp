# gulp
This is a simple repo for managing my gulpfile. This specific gulpfile is for a Jekyll site, which requires some non-standard workarounds. Also, just to raise the level of difficulty, an AngularJS app is nested inside the Jekyll site. Therefore, there are a couple of concat and uglification tasks instead of just one.

The dependencies I used were:
**browser-sync** - testing site/app across multipled devices simultaneously and auto-refresh on css file changes.
  
**childprocess** - Module to support Multiple Process Code Coverage with istanbul. I don't really know what that is but I use to serve up the Jekyll site in leu of the Terminal command `jekyll serve` that is commmonly used for local Jekyll development.
  
**gulp-concat** - Concatenates multiple files together into a single source.
  
**gulp-uglify** - Minifies JavaScript files, removing white space, decreasing file size.
  
**gulp-rename** - Allows for files to be renamed during tasks.
  
**gulp-sass** - Gulp Sass compilation into CSS.
  
**gulp-sourcemaps** - Creates sourcemaps for identifying specific file locations for style rules and JavaScript.
     
**gulp-clean-css** - Minfies CSS files.
     
**del** - Removes files during tasks.
    

Explain the ins-and-outs about the parts of the minifying task.

Explain why minifying won't work with mapping css.
    
Explain the custom Jekyll Serve Task

Explain the watch method

The **watch** task uses the gulp `watch` method to identifychanges made to files. It takes two arguments. The first is a string or an array of files to watch. The second argument is an array of tasks to perform. Put simply, when changes are saved in the file(s) of the first param the task(s) from the second param are fired off.

  - One note of interest, notice the 'globbing patterns' used in this task. These filepaths denoted with multiple or single asterisks simplify the selection of files by way of choosing entire directories and/or files that end in a specific extension type.

Explain the default task
