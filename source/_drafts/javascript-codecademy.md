---
title: javascript_codecademy
tags:
---

1-javascript_jQuery

Introduction
Web pages made with HTML and CSS display static content.
They don't respond to user actions like clicking a mouse or typing a key.
JavaScript and jQuery are used to make web pages interactive.
- JavaScript is a programming language used to create web pages that change in response to user actions.
- jQuery is a collection of prewritten JavaScript code that lets us easily create interactive effects on our site.

<!doctype html><html>
  <head>
  <link href="style.css" rel="stylesheet">
  </head>
  <body>
  ...

  <script src="jquery.min.js"></script>
  <script src="app.js"></script>
  </body></html>



Summary
JavaScript is a programming language used to add interactivity to a web page. jQuery simplifies JavaScript syntax and makes it easier to build interactive web pages that work across multiple browsers.
jQuery enables us to do three main things on a web page:
- Events. Respond to user interactions.
- DOM Manipulation. Modify HTML elements on the page.
- Effects. Add animations.
2-Interactive Website:Push Menu

app.js
var main=function(){

}

$(document).ready(main)
use jQuery to run the main function once the web page has fully loaded.


What does this skeleton do?
- The main function is where we'll write our program.
- The $(document).ready runs the main function as soon as the HTML document has loaded in the browser.

jQuery lets us select HTML elements using CSS selectors.


Select an element
use CSS to select the class 'icon-menu'
$('.icon-menu');

Respond to a click
$('.icon-menu').click();

Open the menu
Clicking on the menu icon should open the menu.
var main=function(){
    $('.icon-menu').click(function()
    {
        $('.menu').animate(
            {
                left:'0px'
            },200
        );
        $('body').animate(
            {
                left:'285px'
            },200
        );
    }
    );
};
Click the menu icon.The menu appears by pushing the body over to the left.

Close the menu
var main=function(){
    $('.icon-menu').click(function()
    {
        $('.menu').animate(
            {
                left:'0px'
            },200
        );
        $('body').animate(
            {
                left:'285px'
            },200
        );
    }
    );
    $('.icon-close').click(function()
        {
            $('.menu').animate({left:"-285px"},200);
            $('body').animate({left:"0px"},200);
        }
    );
};
When you click the menu icon, the menu pushes over from the left. When you click the X icon, the menu pushes back to the right.

3-Interactive Website_javascript

JavaScript is a programming language that jQuery is written in, and knowing JavaScript will be helpful for understanding and writing your code.

Variables store data so that they can be used later on in the program.
It's possible to change a variable's value using basic math.
Variables can also store pieces of text, called strings. A string is written by surrounding text with quotes.
Single quotes or double quotes can be used to write a string.

var tweet="Hiking trip on Saturday";
var tweetLength=tweet.length;

It's possible to compare variables using comparisons.
>     Greater than
<     Less than
>=     Greater than or equal to 
===     Equal to
!==     Not equal to

if
We can use comparisons programs that ask yes or no questions.
if statement
if(myName.length>=7>{
     status="You have a long name!";
}

if...else
if( ){
}
else{
}

if( ){
}
else if( ){
}
else {
}

Functions
Functions contain code that can be used over and over again in a program.
A function is made up of three parts:
1Function name
2Parameters
3Body

var percentage =function(num,denom){
     var result=(num/denom)*100;
     return result;
}

var p1=percentage(23,30);
4-Interactive Website_javascript_

Events
User interactions with a web page are call events.

Event Handlers
We can write a function that specifies what to do when an event occurs.
This function is called an event handler.

var main = function() {
  $(".like-button").click(function() {
  $(this).toggleClass("active");
  });};
$(document).ready(main);
When a user clicks the .like-button element, the event handler toggles the "active" class. This alternates the button between the normal gray view and the selected blue view.

.click()
The .click() method attaches an event handler to an HTML element so that it can respond to a click event.
$('.social li').click(function() {
  $(this).toggleClass('active');
});
The event handler adds the CSS class .active, which changes the button's background-color to red.
We use $(this) to refer to the HTML element that was clicked on. We can now operate on this element using .toggleClass().


Keypress()
Another common user event is the keypress event.A keypress event occurs when a user types a key on the keyboard.
The .keypress() method attaches an event handler to an HTML element so that it can respond to a keypress event.
$(document).keypress(function() {
  $('.dropdown-menu').toggle();
});
$(document) selects the whole web page.
The .keypress() method attaches an event handler to document.
When any keyboard key is pressed, the event handler toggles the dropdown menu.


The event object contains more information about an event, such as which mouse button was clicked or which key was pressed.
$(document).keypress(function(event) {
  if(event.which === 109) {
  $('.dropdown-menu').toggle();
  }
});
$(document) select the whole web page, and the .keypress() method attaches an event handler to document.
The event handler takes event as a parameter.
event.which contains which key was pressed. Keyboard keys are identified by key codes. The m key is identified by the key code 109.

5-Interactive Website_News Reader

Show a description
var main = function() {
  $('.article').click(function() {
  $(this).children('.description').show();
  });
};
In jQuery $(this) refers to the current element or object selected.
childre( ) allows you to search through elements nested directly under the current element.
show( ) is jQuery's way of saying list or display these.

Hide other descriptions
$('.description').hide();

Mark the current article
select all other article using the 'article' class and remove the class 'current' from them using .removeClass( ).
$('.article').removeClass('current');
select the current article using this. Add the class 'current' to it using .addClass( ).
$(this).addClass('current');

Keyboard shortcuts
$(document).keypress(
                function(event)  { }  
      );

Keyboard keys are identified by key codes.
$(document).keypress(
    function(event){
        if(event.which===111)
            $('.current').children('.description').toggle();
    }
);

6-Interactive Website_DOM

DOM Manipulation

$( )
In jQuery, we often see $( ). It has two main uses:
1To select existing HTML elements on the page.
2To create new HTML elements to add to the page.
$('p') selects all p elements on the page.
$('<h1>') create a new h1 element. The < > indicates that we want to create a new HTML element.



.text( )
The .text( ) method adds text to an HTML element.


.appendTo( )
$('.btn').click(function() {
  $('<li>').text('New item').appendTo('.items');
});
The $( ) function creates a new li element.
Text is added to the new li element.
The li element is added as the last item inside <ul class="items">...</ul> on the page.

.prependTo( )
$('.btn').click(function() {
  $('<li>').text('New item').prependTo('.items');
});
The $('<li>') function creates a new li element.
The li element is added as the first item inside <ul class="items"> ...</ul> on the page.

.remove( )
The .remove( ) method removes the selected HTML element from the web page.
$('.btn').click(function() {
  $('.selected').remove();
});
When the Delete button is clicked, the .selected element is removed from the page.

Six jQuery Methods
These six jQuery methods let you control more aspects of HTML elements.
.hide( ) hides the selected HTML element
.show( ) display an element
.toggle( ) alternates hiding and showing an element.
.addClass( ) adds a CSS class to an element
.removeClass( ) removes a class from an element
.toggleClass( ) alternates adding and removing a class freom an element

Notice where .toggleClass( ) is located. You can replace .toggleClass( ) with any of the five other methods. While each method creates different effects, their usage is similar.

Document Object Model
jQuery also comes with methods that let us select HTML elements in relation to other elements.


In the web page to the right, HTML elements are nested inside other elements, forming a hierarchy. This hierarchy can be visualized as a tree.
This representation of HTML is called the Document Object Model(DOM).

DOM Traversal
The DOM is useful to represent relationships between elements, similar to a family tree.

For example, look at the ul element:
The two li elements nested inside are its child elements.
The .article element is its parent element
the h2 and p elements are its sibling elements

.next( )
The .next( ) method gets the next sibling of the selected element.

.prev( )
The .prev( ) method gets the previous sibling of the selected element.


.children( )
The .children( ) method gets the children of the selected element.
If provided a selector, the .children( ) method can get a specific child.


7-Interactive Website:Status Update

Create a new post
var main = function(){
    $('.btn').click(
        function(){
            var post = $('.status-box').val();
            $('<li>').text(post).prependTo('.posts');
        }
    );
}
$(document).ready(main);
- Access the Post button by selecting the 'btn' class.
- Add a .click() method with a function inside. This function is called a click event handler.
- Inside the event handler:
a. Create a variable named post. We want to store what is typed in the status-box in this variable. How? Select the class status-box. Use .val() afterstatus-box is selected. This .val() is like .text() but for form inputs.
- b. Then use $( ) to create a new lielement.
- c. The li element doesn't have any text. Use .text(post) to add text to the element.
- d. But this li element does not show up anywhere. Use .prependTo('.posts')to prepend it to the <ulclass="posts">..</ul> element.

Clear out the status box
$('.status-box').val('');  //clear out the status box by setting its value  to an empty string.

Count characters left
    $('.status-box').keyup(
        function(){
            var postLength=$(this).val().length;
            var charactersLeft=140-postLength;
            $('.counter').text(charactersLeft);
        }
    );
- Outside the click event handler, select the 'status-box' class
- Add a .keyup() method with a function inside. The .keyup() is similar to .keypress(). Therefore, this function is called a keyup event handler.
- Inside the event handler:
a. Create a variable named postLength. In this variable, we want to store the length of the message typed in the status box. Use $(this), .val(), and.length
- b. Create a variable namedcharactersLeft and set it equal to 140 minus postLength
- c. Update the '.counter' to show how many characters are left. Select the'counter' class and use .text() to update its text with charactersLeft

Reset the counter
$('.counter').text('140');

Disable the button 1
The Post button should only work for messages that are 140 characters or less.
            if(charactersLeft<0){
                $('.btn').addClass('disabled');
            }
            else if(charactersLeft===140)
            {
                $('.btn').addClass('disabled');
            }
            else{
                $('.btn').removeClass('disabled');
            }


Disable the button 2
The post button is only enabled when at least one character is typed in the update box.
The line$('.btn').addClass('disabled');disables the Post button after it has been clicked.

8-Interactive  Website_jQuery

jQuery comes with several useful methods that can animate HTML elements in a web page.

.slideDown( )
$('body').click(function() {
  $('.slide').slideDown(600).addClass('active-slide');
});
When you click in the page's body, the next image slides down over 600 milliseconds.

.slideUp( )
.fadeIn( )
.fadeOut()

.animate()
$('.icon-menu').click(function() {
  $('.menu').animate({
  width: "193px"
  },
  300);
});
$('.menu') selects the navigation menu element on the page.
.animate( ) takes two parameters:
1.A set of CSS properties,
2.A time duration over which to change them.
300 milliseconds

9-Interactive Website_Flipboard

Dropdown menu
var main = function() {
  $('.dropdown-toggle').click(function() {
  $('.dropdown-menu').toggle();
  });
}

Next slide 1
    $('.arrow-next').click(
        function()
        {
            var currentSlide=$('.active-slide');
            var nextSlide=currentSlide.next();

            currentSlide.fadeOut(600).removeClass('active-slide');
            nextSlide.fadeIn(600).addClass('active-slide');
        }
    );

Next slide 2
            if(nextSlide.length==0)
            {
                nextSlide=$('.slide').first();
            }

Next dot 1
            var currentDot=$('.active-dot');
            var nextDot=currentDot.next();
            currentDot.removeClass('active-dot');
            nextDot.addClass('active-dot');
            currentSlide.fadeOut(600).removeClass('active-slide');

Next dot 2
nextDot=$('.dot').first();

Previous slide 1
