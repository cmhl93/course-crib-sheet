# Forms

##  Forms
  ```
  <form>
    <label>First Name: 
      <input type = “text” name = “firstName”>
    </label>
    <label for = “lastName”>Last Name: </label>
      <input id = “lastName” type = “text” name = “lastName”>
    <input type = “submit” value = “Submit”>
  </form>
  ```
##  Different types of inputs

  * Email input:
  ```
  <form>
    <label for = “email”>Email:</label>
    <input id = “email” type = “email” name = “email”>
    <input type = “submit” value = “Save!”>
  </form>
  ```
  
  *	Telephone input:
  ```
  <form>
    <label for = “telephone”>Telephone:</label>
      <input id = “telephone” type = “tel” name = “telephone”>
    <input type = “submit” value = “Save!”>
  </form>
  ```

  *	Text input:
  ```
  <form>
    <label for = “yourMessage”>Your Message</label>
      <textarea id = “yourMessage” name = “yourMessage”></textarea>
    <input type = “submit” value = “Save!”>
  </form>
  ```
  
##  Choosing between a set of options
  *	Selector—used when user’s already know what they’re looking for
    *	Ex: which country do you live in? 
    *	Code:
  ```
  <label for = “favoriteColor”> What is your favourite color?</label>
  <select id = “favoriteColor” name = “favoriteColor”>
    <option value = “colorRed”>Red</option>
    <option value = “colorOrange”>Orange</option>
  <option value = “colorYellow”>Yellow</option>
  </select>
  ```
  
  *	Radio—few choices, afford screen space
    *	For more important decisions
    *	Code:
    ```
    <fieldset>
      <legend>What is your favourite meal?</legend>
    <input type = “radio” id = “breakfast” name = “favoriteMeal” value = “meal1”>
      <label for = “breakfast”>Breakfast</label>
    <input type = “radio” id = “brunch” name = “favoriteMeal” value = “meal2”>
      <label for = “brunch”>Brunch</label>
    </fieldset>
    ```
    
  *	Checkbox
    *	Code:
      *	`<input type = “checkbox”>`
      *	The user can select more than one.
