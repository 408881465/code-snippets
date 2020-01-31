[submitting html form without reload the page](https://www.codexpedia.com/javascript/submitting-html-form-without-reload-the-page/)  
Sometimes, when a form is submitted, you don’t want to reload the page, instead you want to execute a javascript function only. Here are ways of executing a javascript function on form submit without reload the html page. **return false**; is the key to prevent the from to reolad the html page.

###### 1. When this html form is submitted, it will call the javascript function yourJsFunction(), but it won’t reload the page.

```
<form action="#" onsubmit="yourJsFunction();return false">
    <input type="text"/>
    <input type="submit"/>
</form>
```
###### 2. Use jQuery’s submit event to handle the form submit, add return false; at the end of the submit handle function to prevent the page to reload.

```
<script src="https://code.jquery.com/jquery-2.2.1.min.js"></script>
<form action="" id="my-form">
    <input type="text"/>
    <input type="submit"/>
</form>
```
```
$(document).ready(function() {
    $(document).on('submit', '#my-form', function() {
      // do your things
      return false;
     });
});
```
###### 3. This form has no submit input, thus it won’t reload the page because the form will never get submitted, but the javascript function will be executed the button input is clicked.
```
<form action="#">
    <input type="text"/>
    <input type="button" onclick="yourJsFunction();"/>
</form>
```
Collect the input values from the form that don’t reload the page.
Referenced from stackoverflow answer
The sample html form with some basic inputs.
```
<form action="" method="post">
    First Name: <input placeholder="First Name" type="text" name="firstname" maxlength="12" size="12"/> <br/><br/>
    Gender:<br/>
    Male:<input type="radio" name="gender" value="Male"/><br/>
    Female:<input type="radio" name="gender" value="Female"/><br/><br/>
 
    Favorite Food:<br/>
    Steak:<input type="checkbox" name="food[]" value="Steak"/><br/>
    Pizza:<input type="checkbox" name="food[]" value="Pizza"/><br/>
    Chicken:<input type="checkbox" name="food[]" value="Chicken"/><br/><br/>
 
    <textarea wrap="physical" cols="20" name="quote" rows="5" placeholder="message"></textarea><br/><br>
 
    Select a Level of Education:<br/>
    <select name="education">
    <option value="Jr.High">Jr.High</option>
    <option value="HighSchool">HighSchool</option>
    <option value="College">College</option></select><br/>
    <p><input type="submit" /></p>
</form>
```
##### JSON 
```
<pre id="result"></pre>
```
The jQuery function for converting the form input values into a json object.
```
$.fn.serializeObject = function(){
    var o = {};
    var a = this.serializeArray();
    $.each(a, function() {
        if (o[this.name] !== undefined) {
            if (!o[this.name].push) {
                o[this.name] = [o[this.name]];
            }
            o[this.name].push(this.value || '');
        } else {
            o[this.name] = this.value || '';
        }
    });
    return o;
};
 
$(function() {
    $('form').submit(function() {
        $('#result').text(JSON.stringify($('form').serializeObject()));
        return false;
    });
});
```
