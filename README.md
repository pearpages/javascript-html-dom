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

---

## CSS

---

## Animations

---

## Events

---

## EventListener

---

## Navigation

---

## Nodes

---

## Nodelist

---