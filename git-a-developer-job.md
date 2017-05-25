Based on the course "Git a Developer Job" by Brad Schiff

<h1>Document Contents:</h1>

<h2>Git Essentials</h2>
<h2>Intro to Node.js & NPM</h2>

<h3 id="#git">Git Essentials</h3>

<h4>What is Git?</h4>
  A version control system
  Git helps use manage our files
  <ul>
    <li>History</li>
    <li>Collaboration</li>
    <li>Feature branches</li>
  </ul>
  
  Vocab
  <ul>
    <li>Project = Repository (repo)</li>
    <li>Working directory = folder location where the project lives</li>
    <li>Commit = Git's way of "saving"</li>
    <li>Staging = Control what gets committed</li>
  </ul>

  Push & Pull
  Git stores system commit data locally, on your hard drive
  <ol>
    <li>Lost your computer? Lose your project</li>
    <li>Collaboration</li>
    Solution: Repo Hosting (GitHub)
  </ol>
  
  Repo on our computer -> push -> Repo on GitHub's server
  Repo on GitHub's server -> pull changes -> Repo on our computer
  
  Command Line - Git Bash
    -pwd - current directory
    -cd - change directory
    -Drag folder onto Git Bash (cd <space> folder)
    -mkdir "hello-world" (Make directory "hello-world")
    -git init (Git initalized)
    -touch "index.html" (Create .html file)
    -git checkout -- . (restore file changes or deletion)
 
  Clone - copy an existing repository from a server to our computer's hard drive
    ex: git clone https://github.com/LearnWebCode/welcome-to-git.git
    
  git remote -v (view current repo location)
  git remote set-url origin <github link> (Change origin)
  
  git push origin master (upload to git site)
  
  To push change:
    git status
    git add -A
    git status
    git commit -m 'Message'
    git push origin master
    
  <h3 id="#npm">Intro to Node.js & NPM</h3>
  
  Automation - take a task and find a way to have your computer do it for you
  
  Example 1:
    -Automatic browser refreshing
    -CSS Autoprefixer
 
 CSS Organization
  -separated into multiple css files
  header.css, footer.css, banner.css, features.css
  Don't link all mini css files
  
  Package management - getting framework files
  
  Node.js
    -JavaScript runtime
    
    node -v (Check version)
    
  node file.js (Run code through node)
   
 NPM - Node Package Management
   -centralized place where developers share their code with the world
   -A package manager can automatically grab fresh copires of all our ingredients
   
 
  
