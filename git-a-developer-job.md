## Document Contents:

[Git Essentials](#git-essentials)

[Intro to Node and NPM](#intro-to-node-and-npm)

[Gulp Essentials](#gulp-essentials)

[CSS Architecture](#css-architecture)

[Gulp Timeout](#gulp-timeout) 

[Mobile-First Essentials](#mobile-first-essentials)      

[Git Branches](#git-branches)

[Automated Sprites](#automated-sprites)

[JavaScript Organization](#javascript-organization)

## Git Essentials

  * What is Git? 
    * A version control system
    * Git helps use manage our files
    * History 
    * Collaboration
    * Feature branches
  
  * Vocab
    * Project = Repository (repo)
    * Working directory = folder location where the project lives
    * Commit = Git's way of "saving"
    * Staging = Control what gets committed

  * Push & Pull
      * Git stores system commit data locally, on your hard drive
        * Lost your computer? Lose your project
        * Collaboration
        * Solution: Repo Hosting (GitHub)
  
  * Repo on our computer -> push -> Repo on GitHub's server
  * Repo on GitHub's server -> pull changes -> Repo on our computer
  
  * Command Line - Git Bash
    * pwd - current directory
    * cd - change directory
    * Drag folder onto Git Bash (cd <space> folder)
    * mkdir "hello-world" (Make directory "hello-world")
    * git init (Git initalized)
    * touch "index.html" (Create .html file)
    * git checkout -- . (restore file changes or deletion)
    
  * Clone - copy an existing repository from a server to our computer's hard drive
    * ex: git clone https://github.com/LearnWebCode/welcome-to-git.git
    
  * View current repo location 
    ` git remote -v` 
  
  * Change origin
    ` git remote set-url origin <github link>`
  
  * Upload to git site
    ` git push origin master` 
  
  * To push change:
    ``` 
    git status
    git add -A
    git status
    git commit -m 'Message'
    git push origin master
    ```
    
## Intro to Node and NPM
  
  * Automation - take a task and find a way to have your computer do it for you
    * Example 1:
      * Automatic browser refreshing
      * CSS Autoprefixer
 
  * CSS Organization
    * separated into multiple css files
      * header.css, footer.css, banner.css, features.css
    * Don't link all mini css files
  
  * Package management - getting framework files
  
  * Node.js
    * JavaScript runtime
      `node -v (Check version)` 
    * node file.js (Run code through node)
   
  * NPM - Node Package Management
    * centralized place where developers share their code with the world
    * A package manager can automatically grab fresh copires of all our ingredients
   
  * 2 Types of Packages
    * Node Packages
      * Automation
      * Build tools
      * Server Tasks
    * Other Things
      * jQuery
      * Bootstrap
      * Normalize.css
  
  * Command Line:
  
    `npm install jquery --save` 
    
    `npm install normalize.css --save`

  * If node modules folder deleted: 
  
    `npm install (redownload packages)`

## Gulp Essentials

  * Gulp Introduction
    * Gulp = automation
  * Installing Gulp
    * Install globally   npm install gulp-cli --global
    * Install in project  npm install gulp --save-dev

  * Check version: 
    `gulp -v`

  * --save -> save to dependencies, packages needed for the browser to run
  * --save-dev -> for developer efficiency

  * Create gulpfile.js:
    `touch gulpfile.js`
  
  * set up package:
  ```
  var gulp = require('gulp');
  gulp.task('default', function(){
    console.log("Hello World");
  });
  ```

  * run default task -> gulp 
  * run specific task -> gulp <name>

  * gulp plugin:
    * Add gulp-watch:
    `npm install gulp-watch --save-dev`
    
  * In gulpfile.js
    * Add:
    ```
    var watch = require('gulp-watch');
    gulp.tasak('watch', function(){
      watch('./app/index.html', function(){
        gulp.start('html');
      });
    });
    ```
    
  * CTRL + C -> Gulp stop watching
    
  * Gulp and PostCSS
    * What is a CSS workflow?
      * Autoprefixer
    * CSS Preprocessors
      * Sass
      * Less
      * Stylus
    * CSS Variables
    * Nested CSS
    * Lets us write code the way we wish, recylces it into a new file that is supported by the browser
    
    * PostCSS
      * Popular new post-processor
      * Fastest to compile out of all pre/post-processors
     
     ``` 
     gulp.src()
     gulp.dest()
     pipe()
     ```
    * Install PostCSS: 
    
      `npm install gulp-postcss --save-dev`
    
    * Install Autoprefixer: 
    
      `npm install autoprefixer --save-dev`
    
    * Install Simple Vars: 
    
      `npm install postcss-simple-vars --save-dev`
    
    * Install nested CSS: 
    
      `npm install postcss-nested --save-dev`
    
## CSS Architecture

  * File architecture
  
  `npm install postcss-import --save-dev`
      
    * Ex: (on main css file)
    
    `@import "base/global.css";`
        
    * Add dependency to project
    
    `@import "normalize.css";`
        
  * What is BEM?
    * Popular abstract way of thinking about our interface
      * B - block (independent, reusuable part of our design)
      * E - element (belongs to a block.  It cannot be used outside of the block that it belongs to)
      * M - modifer (can be used on a block or an element to indicate a change to the default state of an object)
        * toggle classes
        * Button share class "btn", modifier class added to differentiate buttons
    
    * Overview
      * SS selectors should target elements directly with classes, instead of relying on type selectors, descendent selectors, and the cascade.
      * Because we are limiting cascade we are free to move blocks around and reuse them throughout the page
      * Blocks can be nested inside other blocks.
      * Identify patterns and then create single-responsibility blocks.
      
      * There is no reason to code a pattern more than once
      
      * Makes a relationship between our HTML and CSS clear.
        * Ex:
          ```
          class = "large-hero__subtitle"
          block - large-hero
          subtitle - element
          ```
          
      * Nested CSS:
        `&__<element name>{}`
      * Complete Two Blocks:
        * -rem - relative to the root of the page (html element) usually 16px
        
        * Add modifier:
          * Ex: class = "btn--large"
      
## Gulp Timeout     

  Install BrowserSync:
    npm install browser-sync --save-dev
    
    In gulpfile.js:
    browserSync = require('browser-synce');
    browserSync.init({
      server: {
        baseDir: "app"
      }
    });
    
    Auto-refresh:
      browserSync.reload();
      
    -Cross Mobile Testing Capabilities
    -Use External address to test on mobile
    
  Organizing our gulp.js file:
    separate js files
    copy variables required for each js file
    import into main gulp:
      require('./gulp/tasks/styles'); 
        Don't need extension (.js) when using require
        
  Gulp Error Handling:
    In styles.js:
      .on('error', function(errorInfo)){
        console.log(errorInfo.toString());
        this.emit('emit');
      });
      
## Mobile-First Essentials

  What does "mobile-first" mean?
    Building responsive web pages starting from mobile devices
      Why?
        More traffic from mobile devices than traditional desktops and laptops
          Our primaryy source of traffic should not be an afterthought
        Traditional "desktop-first" responsive design resulted in bloated slow loading desktops
          We don't want anyone to have to download extra data that they won't even use
   Mobile-first = efficient websites that load as quickly as possible for everyone
   
   Mobile first in different contexts
    Design context
      Desiging around a smaller screen first
      Force us to prioritize our content
      Anticipate more common user actions
      Information architects, graphic designers, usuability experts.
    Development Context
      Coding the site so devices don't download unnecessary data
      Treat the most essential view of our website as our baseline and code upwards from there
      Make the site load quickly for everyone
      
    Where do we begin with mobile-first development?
      -HTML
      -CSS
      -JavaScript
      
      Mixins:
        npm install postcss-mixins --save-dev
        
        @define-mixin atSmall
        @mixin atSmall
        
      Responsive Images
        Reasons to use responsive images
          1. Art direction & cropping situation
            <picture>
              <source srcset="images/dog-crop-large.jpg" media="(min-width: 1200px)">
              <source srcset="images/dog-crop-medium.jpg" media="(min-width: 760px)">
              <img src="images/dog-crop-small.jpg" alt="Puppy in the sand">
            </picture>
          2. Image resolution & file size situation (faster load times)
            <img srcset="images/dog-resolution-small.jpg 570w, images/dog-resolution-medium.jpg 1200w, images/dog-resolution-large.jpg 1920w" alt="Puppy in the Sand">
            
     Quick Tips for testing, responsive images
      Add counterparts of images-dark overlay pixel size
      Simulating and testing pixels:
        Inspect-> device icon
        
    //Other
      In-line element - the browser thinks it's similar to a line of text
      em -> relative to the font size
      
      Too many modifier classes?
        -easier to create than unique classes
        Ex: new style updates
        Avoid spaghetti CSS
        
        When we float an element, we take it out of the normal flow of the page.
          -Clear floats:
            &::after{
              content: "";
              clear: both;
              display: table;
            }
      font-weight: 400 -> standard
      
## Git Branches

    git branch -> will list all the branches in the repo
    "master" branch as the...
      primary, main, live, production
    ...version of our project
    
    Create a new branch for each new feature of our project
    
    How to create a new branch
      need clean directory
        git status
      remove file from staging area:
        git reset <path to file>
        
      git branch <name of branch>
      
      Star next to branch - current branch we're working in
      
    Switch branch (Checkout)
      git checkout count-to-ten
      
    Merge changes in one branch to master branch
      -switch back to master
        git merge <name of branch>
      -commits from other branch will show after merge and push
      
    Merge through GitHub
      -small change, stage and commit files in one line
      git commit -am 'Message'
      git push origin <name of branch>
      Open a pull request, assign to another developer for review
        Merge pull request
        
      git pull master
      
      git branch -d <name of branch> (Delete locally)
      git push origin --delete <name of branch> (Delete remote)
      
      Create and switch to branch in one move: git checkout -b <name of branch>
      
      Merge branch into master
        git merge our-features --no-ff
          esc
          wq
          Enter
          
          Creates a dedicated commit in your repo's history
          
## Automated Sprites

What is an icon sprite?
  All icons on one sheet
  .svg format
  gulp can create sprite sheets
    npm install gulp-svg-sprite @1.3.1 --save dev
    
  on gulpfile.js:
    require('./gulp/tasks/sprites');
    
    Create a new sprites.j (in gulp/tasks folder) and add:
      var gulp = require('gulp'), svgSprite = require('gulp-svg-sprite');
      var config = {
        mode:{
          css:{
          
          }
        }
      }
      
    gulp.task('createSprite', function(){
      return gulp.src('./app/assets/images/icons/**/*.svg')
        .pipe(svgSprite(config))
        .pipe(gulp.dest('./app/temp/sprite/'));
    });
    
    gulp createSprite in command line (Creates spritesheet)
    
    Use spritesheet to use certain icons in certain location
      In sprites.js:
        var config -> mode ->css
        
        render:{
          css:{
            template: './gulp/templates/sprite.css'
          }
        }
        
     Create template folder in gulp folder
      create a sprite.css
        Add:
          {{#shapes}}
            .icon--{{base}}{
              width: {{width.outer}}px;
              height: {{height.outer}}px;
              background-image: url('/temp/sprite/css{{{sprite}}}');
              background-position: {{position.relative.xy}};
            }
          {{/shapes}}
          
     gulp createSprite
      creates new sprites.css with icons position selected
      
    Use spritesheet to use certain icons in certain places:
      import generated sprite sheet into main css file
        use gulp to move file to modules folder
       
       install package:
        npm install gulp-rename --save-dev
        
        Add var rename = require('gulp-rename');
        
        keep image class, delete everything else
          Delete old sprites:
            npm install del --save-dev
        
      In sprites.js, add:
        gulp.task('copySpriteCSS', function(){
          return gulp.src('./app/temp/sprite/css/*.css')
            .pipe(rename('_sprite.css'))
            .pipe(gulp.dest('./app/assets/styles/modules'));
        });
        
        gulp copySpriteCSS (command line)
          generates sprite.css in modules folder
          
        Use variables in rgba:
          npm install postcss-hexrgba --save-dev
          
## JavaScript Organization

  Intro to Object-Oriented Programming
    -Stop thinking in terms of individual variables and functions
    -Begin thinking in terms of cohesive, self-sufficient objects
    
    Object:
      data and behavior
      nouns and verbs
      
    "this" keyword
      allows function to be recyclable
      
    Ex:
    function Person(fullName, favColor){
      this.name = fullName;
      this.favoriteColor = favColor;
      this.greet = function(){
        console.log("Hello, my name is " + this.name + " and my favorite color is " +this.favoriteColor + ".");
      }
    }
      
    
    var john = new Person("John Doe", "blue");
    john.greet(); //Hello, my name is John Doe and my favorite color is blue
    
    var jane = new Person("Jane Smith","green");
    jane.greet(); //Hello, my name is Jane Smith and my favorite color is green
    
    Store that "function" (class) separately using WebPack
    
    The JS Module Pattern and "WebPack"
      -installing webpack
        npm install webpack -g  
      -Create "webpack.config.js" in root folder (beside package.json)
      -Command line: enter "webpack"
      -Can Install JQuert:
        npm install jquery --save
        
        in js file:
          var $ = require('jquery');
          
      Install webpack so that it will automatically rebundle when js file is saved
        -Install webpack locally:
          npm install webpack --save-dev
          
    Babel:
      -Modern JavaScript with browser support
      -ECMAScript is the standard for JavaScript that web broswers are encouraged to follow
      
      Write ES6 code -> Babel compiles it into ES5 code
      
      Install and setup Babel
        npm install babel-core babel-loader babel-preset-es2015 --save-dev
        
      Inheritance
      
      <h3>Revealing Elements on Scroll</h3>
      npm install waypoints --save
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
     
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
