##  Sublime Text Settings

  Preferences > Settings - User
  
  Save file located in Packages folder
  
  All saves will over Settings - Default
  
  Preferences > Browse Packages > User folder
  
  Language specific settings files
  
  When adding more settings, remove trailing commas
  
  Preferences > Settings - Default
  
  All default saves
  
##  Bookmarking

  CTRL + F2 Toggle bookmarks
  
  F2 Next bookmarks
  
  Shift + F2 Previoous bookmarks

  ALT + F2 Select all bookmarks
  
  CTRL + SHIFT + F2 Clear all bookmarks
  
##  The Command Palette

  CTRL + SHIFT + P
  
  Opens up features in the editor
  
  fuzzy search -> predictive based on search
  
  ssx -> Set Syntax
  
  Rename file -> search file:rename
  
  Emmet -> Edit code
  
  Origami - > manage your panes
  
##  Master GOTO anything 

  Used for navigation to a file or to certain places in a file
  
  CTRL + P open GOTO anything
  
  search file name
  
  Once your inside a file, to go to a line number: enter ": + line number"
  
  To find a class name: enter "@classname + classname"
  
  Goto symbol in project -> symbols in the entire project
  
##  Predictive File Name Typing  

  Download package control from https://packagecontrol.io/
  
  Open up Command Palette
  
  Install Package Controll
  
  Search autofile name and install
  
  Autofile quick settings -> Disable HTML image dimension insertion
  
##  Code Folding

  Click fold button in gutter to tidy large blocks of code.
  Do not delete the yellow horizontal symbol or it will delete all of the code.
  
  Keyboard shortcut: Select code then press CTRL + SHIFT + [
  
  Unfold: CTRL + SHIFT + ]
  
  Unfold all at once: CTRL + K & CTRL + J
  
  Block level folding: CTRL + K + Level of indentation
  
  Remember: Cursor must not be inside block during folding in order to do block level folding
  
  Fold image attributes: CTRL + K & CTRL + T
  
##  Creating and Using Snippets

  Snippets are reusable pieces of code
  
  Available snippets: Tools > Snippets
  
  Create snippet: Tools > new snippet
  
  ```
  <snippet>
	<content><![CDATA[
  html {
    box-sizing: border-box;
  }
  *, *:before, *:after {
    box-sizing: inherit;
  }
  ]]></content>
    <!-- Optional: Set a tabTrigger to define how to trigger the snippet -->
    <tabTrigger>.bbox</tabTrigger> (What is written before pressing Tab, . added to override Emmet plugin)
    <!-- Optional: Set a scope to limit where the snippet will trigger -->
    <scope>source.css, source.scss, source.sass, source.less, source.stylus</scope>  (Applied to which type of files)
    <description>Border box css snippet for implementing box-sizing</description> (Description when searching in command palette)
  </snippet>
  ```
  
  save in snippets folder with the extension .sublime-snippet
  
  Find snippets at Github:
  
  Code options with this extension: .sublime-snippet
  
##  Moving, Jumping, Selecting and Inserting



##  Some useful shortcuts

### Editing

  Ctrl + X	Cut line
  Ctrl + ↩	Insert line after
  Ctrl + ⇧ + ↩	Insert line before
  Ctrl + ⇧ + ↑	Move line/selection up
  Ctrl + ⇧ + ↓	Move line/selection down
  Ctrl + L	Select line - Repeat to select next lines
  Ctrl + D	Select word - Repeat select others occurrences
  Ctrl + M	Jump to closing parentheses Repeat to jump to opening parentheses
  Ctrl + ⇧ + M	Select all contents of the current parentheses
  Ctrl + ⇧ + K	Delete Line
  Ctrl + KK	Delete from cursor to end of line
  Ctrl + K + ⌫	Delete from cursor to start of line
  Ctrl + ]	Indent current line(s)
  Ctrl + [	Un-indent current line(s)
  Ctrl + ⇧ + D	Duplicate line(s)
  Ctrl + J	Join line below to the end of the current line
  Ctrl + /	Comment/un-comment current line
  Ctrl + ⇧ + /	Block comment current selection
  Ctrl + Y	Redo, or repeat last keyboard shortcut command
  Ctrl + ⇧ + V	Paste and indent correctly
  Ctrl + Space	Select next auto-complete suggestion
  Ctrl + U	soft undo; jumps to your last change before undoing change when repeated
  Alt + ⇧ + W	Wrap Selection in html tag
  Alt + .	Close current html tag
  
### Windows

  Ctrl + Alt + Up	Column selection up
  Ctrl + Alt + Down	Column selection down
  
### Navigation/Goto Anywhere

  Ctrl + P	Quick-open files by name
  Ctrl + R	Goto symbol
  Ctrl + ;	Goto word in current file
  Ctrl + G	Goto line in current file

### General 

  Ctrl + ⇧ + P	Command prompt
  Ctrl + KB	Toggle side bar
  Ctrl + ⇧ + Alt + P	Show scope in status bar
  
### Find/Replace

  Ctrl + F	Find
  Ctrl + H	Replace
  Ctrl + ⇧ + F	Find in files

### Tabs

  Ctrl + ⇧ + t	Open last closed tab
  Ctrl + PgUp	Cycle up through tabs
  Ctrl + PgDn	Cycle down through tabs
  Ctrl + ⇆	Find in files
  Ctrl + W	Close current tab
  Alt + [NUM]	Switch to tab number [NUM] where [NUM] <= number of tabs
  
### Split window

  Alt + ⇧ + 1	Revert view to single column
  Alt + ⇧ + 2	Split view into two columns
  Alt + ⇧ + 3	Split view into three columns
  Alt + ⇧ + 4	Split view into four columns
  Alt + ⇧ + 5	Set view to grid (4 groups)
  Alt + ⇧ + 8	Split view into two rows
  Ctrl + [NUM]	Jump to group where num is 1-4
  Ctrl + ⇧ + [NUM]	Move file to specified group where num is 1-4

### Text manipulation

  Ctrl + KU	Transform to Uppercase
  Ctrl + KL	Transform to Lowercase  
