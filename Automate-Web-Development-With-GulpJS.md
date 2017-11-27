## Document Contents

[Getting Setup](getting-setup)

[Your First Gulp Task](your-first-gulp-task)

[Gulp Watch Live Reload](gulp-watch-live-reload)

[CSS SCSS and LESS with Gulp](css-scss-and-less-with-gulp)

[JavaScript with Gulp](javascript-with-gulp)

[Other Awesome Plugins](other-awesome-plugins)

##  Getting Setup
  
  ### Installing Node and NPM
    * Node: 
      * Download from Nodejs.org
      * Check node version:
      
        `node -v`
        
    * NPM:
      * Node package modules
      * Ex: Gulp
      * Check npm version:
      
        `npm -v`
  
  ### Using the terminal, it's not that bad!
    * Echo "Text" -->  outputs "Text"
    * cd          -->  change directory
    * ls          -->  list contents of the current folder you're in
    * pwd         -->  print working directory
    * cd ..       -->  go back a directory
    * clear         -->  cleans existing output
    
  ### Installing Gulp
  
    `npm install gulp -g`
    * add sudo in front of command if it fails (OSX or Linux)
    
## Your First Gulp Task
  
  ### NPM Package.json
    * To create Package.json file, type in the command line:
    
      `npm init`
  
  ### Installing Gulp Locally Gulpfile.js
  
    `npm install gulp --save`
    
    * Reinstall existing node modules:
    
      `npm install`
    
    * Create a gulpfile.js file to run tasks
    
      `touch gulpfile.js`
    
  ### Creating Your First Gulp Tasks
    
    ```
    var gulp = require('gulp');

    // Styles
    gulp.task('styles', function(){
      console.log('starting styles task');
    });

    // Scripts
    gulp.task('scripts', function(){
      console.log('starting scripts task');
    });

    // Images
    gulp.task('images', function(){
      console.log('starting images task');
    });
    
    //  Default (when you type only gulp in the command line)
    gulp.task('default', function(){
      console.log('starting default task');
    });

    ```
    
  ### Your First Gulp Plugin
    * Uglify
      * Concatenates and optimizes multiple js files.
      * `npm install --save-dev gulp-uglify`
      * In gulpfile.js
        ```
        var gulp = require('gulp'),
        uglify = require('gulp-uglify');

        // Styles
        gulp.task('styles', function(){
          console.log('starting styles task');
        });

        // Scripts
        gulp.task('scripts', function(){
          console.log('starting scripts task');

          return gulp.src('public/scripts/*.js')
            .pipe(uglify())
            .pipe(gulp.dest('public/dist'));
        });

        // Images
        gulp.task('images', function(){
          console.log('starting images task');
        });

        //	Default
        gulp.task('default', function(){
          console.log('starting default task');
        });

        ```
        
## Gulp Watch Live Reload

  ### Setting Up A Server
  ### Gulp Watch
  ### Live Reload
  
## CSS SCSS and LESS with Gulp


## JavaScript with Gulp


## Other Awesome Plugins

