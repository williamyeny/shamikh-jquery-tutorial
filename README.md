# shamikh-jquery-tutorial
to EDUCATE SHAMIKH

## $ and the selector

You use `$` to select elements.

You specify which elements you want to select by using CSS selectors.
```
$("div"); // this represents all elements that are divs

$("#hello"); // this represents the element with ID "hello"

$("a[href*='expand']"); // this represents all "a" elements that has an href with the substring "expand" in it
```
Remember, `$` only accepts strings!

`$(div); // this gives an error`

## Changing and retrieving properties of elements

Let's say you want to change the HTML of an element with ID "greeting" to "hello"

`$("#greeting").html("hello");`

What if you want to get the HTML contents of said element?

`var contents = $("#greeting").html(); // value of "contents": "hello"`

Setting an attribute of the element?

`$("#greeting").attr("class", "top-text") // changes the class`

Retrieve the attribute?

`var class = $("#greeting").attr("class"); // value of "class": "top-text"`

Changing the css of the element?

`$("#greeting").css("color", "green"); // the text color is now green`

What about appending HTML to an element?

`$("body").append("<p>hey dudes!</p>"); // the paragraph with text "hey dudes!" is added to the body`

## Listening to and triggering events

Let's say you want to know when an element with ID "button" is clicked.

Here's how you would do it:
```
$("#button").on("click", function() {
  // code in here executes when click happens
});
```
What if you want to click on the "button" element programmatically?

`$("#button").click(); // if it is a link, it will take you to whatever site in your browser

For more advanced events, read the jQuery documentation.

## What is "this"?

Let's say you want a `p` element's text to turn orange when you click it. So you write this code:

```
$("p").on("click", function() {
  $("p").css("color","orange");
});
```

Looks good, right? Except when you click on one `p` element, it turns *all* the `p` elements orange.

Why? Because `$("p")` selects every `p` element, remember? So how would you only change the color of the one you clicked?
```
$("p").on("click", function() {
  $(this).css("color","orange");
});
```

The `this` selector is not a CSS selector! It represents the specific element that triggered the event. 

Here's another example:

```
$("iframe").on("load", function() {
  console.log($(this).attr("id")); // when an iframe is finished loading, print its ID.
});
