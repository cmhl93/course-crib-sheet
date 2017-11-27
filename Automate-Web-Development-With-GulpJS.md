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
  
    * `npm install static-server@2.0.0 --save`
    * create a server.js file in the root of the project
    * Add in the server.js file:
      ```
      var StaticServer = require('static-server');

      var server = new StaticServer({
        rootPath: './public/',
        port: 3000
      });

      server.start(function(){
        console.log('Server started on port ' + server.port);
      });
      ```
    * You can now view the project on localhost:3000
    
  ### Gulp Watch
  
    * Watches files and runs gulp tasks in the background to update the files when browser reloads
    * `npm install gulp-watch --save-dev`
    * In gulpfile.js file:
      ```
      var gulp = require('gulp'),
      uglify = require('gulp-uglify'),
      watch = require('gulp-watch');

      // File paths
      var SCRIPTS_PATH = 'public/scripts/**/*.js'

      // Styles
      gulp.task('styles', function(){
        console.log('starting styles task');
      });

      // Scripts
      gulp.task('scripts', function(){
        console.log('starting scripts task');

        return gulp.src(SCRIPTS_PATH)
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

      gulp.task('watch', function(){
        console.log('starting watch task');
        require('./server.js');
        gulp.watch(SCRIPTS_PATH,['scripts']);

      });

      ```
        
  ### Live Reload
    
    * `npm install gulp-livereload@3.8.1 --save-dev`
    * 
  
  
## CSS SCSS and LESS with Gulp


## JavaScript with Gulp


## Other Awesome Plugins

