# Javascript HTML

> DOM: Document Object Model

* Core DOM - standard model for all document types
* XML DOM - standard model for XML documents
* HTML DOM - standard model for HTML documents

> The HTML DOM is a standard for how to get, change, add, or delete HTML elements.

JavaScript can :

* change / remove / add elements in the page
* change / remove / add attributes in the page
* change all CSS styles in the page
* react and create events in the page

---

## Methods

In the DOM, all HTML elements are defined as **objects**.

A **property** is a value that you can get or set (like changing the content of an HTML element).

A **method** is an action you can do (like add or deleting an HTML element).

```javascript
<html>
<body>

<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = "Hello World!";
// getElementById is a 'method'
// innerHTML is a 'property'
</script>

</body>
</html>
```

* getElementById
* innerHTML

> The innerHTML property can be used to get or change any HTML element, including <html> and <body>.

---

## Document

### Finding Elements

* document.getElementById(id)
* document.getElementsByTagName(name)
* document.getElementsByClassName(name)

### Changing HTML Elements

* element.innerHTML = html
* element.attribute = value
* element.setAttribute(attribute,value)
* element.stye.property = style

### Adding and Deleting Elements

* document.createElement(element)	
* document.removeChild(element)	
* document.appendChild(element)	
* document.replaceChild(element)	
* document.write(text)	

### Adding Events Handlers

* document.getElementById(id).onclick = function(){code}

### Finding HTML objects

document.anchors	<a>
document.baseURI	Returns the absolute base URI of the document	3
document.body	<body>
document.cookie	
document.documentElement	<html>
document.documentURI	
document.domain	
document.embeds	<embed>
document.forms	<form>
document.head	<head>
document.images	<img>
document.links	all <area> and <a> elements that have a href
document.readyState	Returns the (loading) status of the document
document.referrer	Returns the URI of the referrer (the linking document)
document.scripts	<script>
document.title	<title>
document.URL

---

## Elements

```javascript
var myElement = document.getElementById("intro");

var allP = document.getElementsByTagName("p");

var allIntroClasses = document.getElementsByClassName("intro");
```

This example finds the element with id="main", and then finds all <p> elements inside "main":

```javascript
var x = document.getElementById("main");
var y = x.getElementsByTagName("p");
```

### By Query Selector

```javascript
// also querySelector
var x = document.querySelectorAll("p.intro");
```

---

## HTML

> Never use document.write() after the document is loaded. It will overwrite the document.

* innerHTML
* attribute

```javascript
document.getElementById("myImage").src = "landscape.jpg";
```

---

## CSS

```javascript
document.getElementById("p2").style.color = "blue";
```

```javascript
<h1 id="id1">My Heading 1</h1>

<button type="button" 
onclick="document.getElementById('id1').style.color = 'red'">
Click Me!</button>
```

```javascript
<p id="p1">
This is a text.
This is a text.
This is a text.
This is a text.
</p>

<input type="button" value="Hide text" onclick="document.getElementById('p1').style.visibility='hidden'">
<input type="button" value="Show text" onclick="document.getElementById('p1').style.visibility='visible'">
```

---

## Animations

```javascript
<!DOCTYPE html>
<html>
<style>
#container {
  width: 400px;
  height: 400px;
  position: relative;
  background: yellow;
}
#animate {
  width: 50px;
  height: 50px;
  position: absolute;
  background-color: red;
}
</style>
<body>

<p>
<button onclick="myMove()">Click Me</button>
</p> 

<div id ="container">
<div id ="animate"></div>
</div>

<script>
function myMove() {
  var elem = document.getElementById("animate");   
  var pos = 0;
  var id = setInterval(frame, 5);
  function frame() {
    if (pos == 350) {
      clearInterval(id);
    } else {
      pos++; 
      elem.style.top = pos + 'px'; 
      elem.style.left = pos + 'px'; 
    }
  }
}
</script>

</body>
</html>
```

---

## Events

```javascript
<!DOCTYPE html>
<html>
<body>

<h1 onclick="this.innerHTML = 'Ooops!'">Click on this text!</h1>

</body>
</html>
```

```javascript
<!DOCTYPE html>
<html>
<body>

<h1 onclick="changeText(this)">Click on this text!</h1>

<script>
function changeText(id) { 
    id.innerHTML = "Ooops!";
}
</script>

</body>
</html>
```

### Event attributes

e.g. 

* onclick
* onload
* onchange
* onmouseover
* onmouseout
* onmousedown
* onmouseup
* onfocus

```html
<button onclick="displayDate()">The time is?</button>
```

### Assign Events Using the HTML DOM

```javascript
document.getElementById("myBtn").onclick = displayDate;
```

### The onload and onunload Events

The onload and onunload events are triggered when the user **enters or leaves the page**.

The onload event can be used to check the visitor's browser type and browser version, and load the proper version of the web page based on the information.

The onload and onunload events can be used to deal with **cookies**.

```html
<body onload="checkCookies()">
```

```html
<!DOCTYPE html>
<html>
<body onload="checkCookies()">

<p id="demo"></p>

<script>
function checkCookies() {
    var text = "";
    if (navigator.cookieEnabled == true) {
        text = "Cookies are enabled.";
    } else {
        text = "Cookies are not enabled.";
    }
    document.getElementById("demo").innerHTML = text;
}
</script>

</body>
</html> 
```

### The onchange Event

```html
<input type="text" id="fname" onchange="upperCase()">
```

### The onmouseover and onmouseout Events

```html
<!DOCTYPE html>
<html>
<body>

<div onmouseover="mOver(this)" onmouseout="mOut(this)" 
style="background-color:#D94A38;width:120px;height:20px;padding:40px;">
Mouse Over Me</div>

<script>
function mOver(obj) {
    obj.innerHTML = "Thank You"
}

function mOut(obj) {
    obj.innerHTML = "Mouse Over Me"
}
</script>

</body>
</html> 
```

### The onmousedown, onmouseup and onclick Events

```html
<!DOCTYPE html>
<html>
<body>

<div onmousedown="mDown(this)" onmouseup="mUp(this)"
style="background-color:#D94A38;width:90px;height:20px;padding:40px;">
Click Me</div>

<script>
function mDown(obj) {
    obj.style.backgroundColor = "#1ec5e5";
    obj.innerHTML = "Release Me";
}

function mUp(obj) {
    obj.style.backgroundColor="#D94A38";
    obj.innerHTML="Thank You";
}
</script>

</body>
</html> 
```

[HTML DOM Event Object Reference](http://www.w3schools.com/jsref/dom_obj_event.asp)

---

## EventListener

---

## Navigation

---

## Nodes

---

## Nodelist

---