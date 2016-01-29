
# Javascript on the Web
After this lesson, you'll be able to understand:
+ The browser represents html pages with the document object model (DOM)
+ We can use javascript and jQuery to select and modify elements

So far, we have used javascript to do some math and work with some data. Today, we get to use javascript on its home turf - manipulating HTML elements in the browser.

Let’s start with a little example, to give you a taste of the power of javascript before getting into the nitty-gritty of the DOM.


1. Go to https://twitter.com/taylorswift13
2. Open the console using <kbd>Command</kbd>+<kbd>Option</kbd>+<kbd>j</kbd>
3. Run these two statements, with replacing 'Your Name' with, you guessed it, your name:
  * `names = $('.fullname');`

  * `names.text('Your Name');`

4. Look at the tweets Taylor has sent out very closely



BAM! You are a twitter master! How cool are you! So popular!

Now, how did that work?
##The DOM
Your browser keeps all of the elements of the webpage in a tree structure called the Document Object Model. Basically, it keeps track of all of the html elements from the html page, their styles, and the relationships between them - who is nested in who, which elements have which parents and children.
```html
 <body>
  <ul>
    <li>
      <p>Shady Grove</p>
      <p>Aeolian</p>
    </li>
    <li>
      <p>Over the River, Charlie</p>
      <p>Dorian</p>
    </li>
  </ul>
</body>
```
A way to visualize the DOM for that table would be:

![Tree representation of the elements above](http://i.imgur.com/8fj2Uka.png)

Javascript can speak the browser’s language - it IS the browser’s language. It is AWESOME for picking elements on a webpage and doing something to them - like picking all the elements on the twitter page and changing them to my name.


### The Twitter DOM
Let’s look a little bit more closely at the code we ran to change Twitter. First, in the console, click on the tab that says "Elements". This will show you what the DOM looks like for Taylor's Twitter page. Just like most pages it has a `<head>` and  a `<body>`. It also has a ton  of `<div>` tags, which is what makes the Twitter layout so clean. 

In your first statement,  `names = $('.fullname');`, the $ symbol was used to *select* every element in the DOM with the class `'fullname'` and store it in a new array, names.

The names array looks like this:
```
names = [
<b class="fullname">Selena Gomez</b>,
<strong class="fullname" data-aria-label-part="">Lorde</strong>,
<strong class="fullname" data-aria-label-part="">Gigi Hadid</strong>
]
```

The next bit of code in your console: `names.text('Your Name');`, is what changed all of those elements in your names array.

The  - `.text()` method accesses the text inside an element: 'Selena Gomez', 'Lorde', 'Gigi Hadid'.


Since we passed the .text method a string - 'Your Name'-  all of that text inside every element in the `names` array was changed to 'Your Name'

```
names = [
<b class="fullname">Your Name</b>,
<strong class="fullname" data-aria-label-part="">Your Name</strong>,
<strong class="fullname" data-aria-label-part="">Your Name</strong>
]
```

Try selecting other html elements on the page and updating their text! What happens?
You can do this by going back to the "Elements" tab and looking at what the different ids and classes are.

* *#id*: $("#lastname")	- to select an id, use the # sign
* *.class*: 	$(".intro")	- to select a class, use the . 

The selector syntax - $() - and the .text() method actually aren't part of the javascript baked into the browser. They actually come from the jQuery library - a big, commonly used set of useful javascript functions. In order to use this syntax on our pages, we'll need to link up to a javascript library.

PS. While the names of the methods like .text() make sense when you read them, you probably can't figure them out by guessing. Instead, you can look up all the available methods in the online documentation. If you want to do something specific, it’s usually faster to search for it on google, and check for good StackOverflow answers than try to guess the method name yourself.

### References
[W3 Schools jQuery Selectors](http://www.w3schools.com/jquery/jquery_ref_selectors.asp)

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/cssi-3-js-on-the-web-walkthrough' title='Javascript on the Web'>Javascript on the Web</a> on Learn.co and start learning to code for free.</p>
