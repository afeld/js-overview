!SLIDE

# JavaScript

## the little language everyone loves to hate

### [@aidanfeldman](https://twitter.com/aidanfeldman)

!SLIDE

# moi

* [Education Hacker](https://github.com/blog/1617-aidan-feldman-is-a-githubber), [GitHub](https://github.com)
* Instructor, [NYU](http://scps.nyu.edu/)
* Organizer, [Hacker Hours](http://hackerhours.org)
* Author, *[Developing a Backbone.js Edge](http://www.amazon.com/Developing-a-Backbone-js-Edge-ebook/dp/B00CBP7N3O)*

!SLIDE

# The Highlights

* interpreted, scripting language
* weakly (bad-duck) typed
* single-threaded
* first-class functions
* prototypal inheritance

!SLIDE

# The History

* designed in a week by Brendan Eich for Netscape
* inspired by Self and Scheme, *not* Java
* server-side since 1994, popularized by Node.js
* "JavaScript" trademark owned by Sun, so formal name is "ECMAScript"

!SLIDE

# The Browser Wars

* started in late 90's as IE replaced Netscape
* huge leaps in JS VM speed

!SLIDE

![speed chart](assets/vm_speed.png)

[iq12.com/old_blog/as3-benchmark/](http://iq12.com/old_blog/as3-benchmark/)


!SLIDE

# Types

* primitives (pass by value)
    * string
    * boolean
    * number
* objects (pass by reference)
    * objects
    * arrays
    * functions

!SLIDE

# Numbers

* the only numeric datatype
* floating point! (not "hardcore")

!SLIDE

# Functions

First-class!

    @@@javascript
    var myFun = function(){
      return 'foo';
    };
    myFun(); // 'foo'

    var otherRef = myFun;
    otherRef(); // 'foo'

!SLIDE

# Evented

    @@@javascript
    var elements = $('.submit');
    elements.on('click', function(){
      alert('Thanks for buying!');
    });

!SLIDE

# Scope

Functional, not block-level (C-style)

    @@@javascript
    if (true) {
      var foo = 6;
    }

    foo; // 6

!SLIDE

# Scope (cont.)

    @@@javascript
    var outer = function(){
      var foo = 6;
      var inner = function(){
        return foo;
      };

      inner(); // 6
    };

!SLIDE

# Closures

    @@@javascript
    var wrapper = function(){
      var foo = 6;
      var inner = function(){
        return foo;
      };
      return inner;
    };

    var wrapped = wrapper();
    wrapped(); // 6

.notes show binding of context?

!SLIDE

# Context

    @@@javascript
    var myVariable = "I'm global!";

    function printMyVariable(){
      return this.myVariable;
    }

    printMyVariable(); // "I'm global!"

    printMyVariable.apply({ myVariable: "I'm local!" }); // "I'm local!"

.notes too detailed?

!SLIDE

# Fake OOP

    @@@javascript
    var Person = function(first, last){
      this.first = first;
      this.last = last;
    };

    var bob = new Person('Bob', 'Hope');
    var sally = new Person('Sally', 'Field');

    bob.first; // 'Bob'

!SLIDE

# Namespacing

!SLIDE

# Namespacing

nope.

!SLIDE

# Namespacing

    @@@javascript
    var app = {}; // global
    app.views = {};
    app.views.sidebar = {};

!SLIDE

# Transpiling

* CoffeeScript
* TypeScript

!SLIDE

# Coming Up

!SLIDE

# Coming Up

## ES6

* Object.observe
* modules
* getters and setters
* generators

!SLIDE

# Coming Up

## asm.js

[demo](https://blog.mozilla.org/blog/2013/03/27/mozilla-is-unlocking-the-power-of-the-web-as-a-platform-for-gaming/)

!SLIDE

# Frameworks

!SLIDE

# Frameworks

## Utilities

* jQuery
* Underscore

!SLIDE

# Frameworks

## Basic MVC

* Backbone
* Spine

!SLIDE

# Frameworks

## Data Binding

* [Angular](http://angularjs.org/)
* [Ember](http://emberjs.com/)

!SLIDE

# Frameworks

## UI

* Sproutcore
* jQuery UI
* jQuery Mobile
* Bootstrap

!SLIDE

# See Also

* http://www.youtube.com/watch?v=hQVTIJBZook
* asm.js
  * https://blog.mozilla.org/blog/2013/03/27/mozilla-is-unlocking-the-power-of-the-web-as-a-platform-for-gaming/
  * http://ejohn.org/blog/asmjs-javascript-compile-target/
* performance history
    * http://blog.chromium.org/2010/12/new-crankshaft-for-v8.html
    * http://iq12.com/old_blog/as3-benchmark/s
* https://docs.google.com/presentation/d/1Gv-dvU-yy6WY7SiNJ9QRo9XayPS6N2jtgWezdRpoI04/edit#slide=id.p
* https://github.com/afeld/advanced_js#resources

!SLIDE

# Fin.

Aidan Feldman

[@aidanfeldman](https://twitter.com/aidanfeldman)

[api.afeld.me](http://api.afeld.me)
