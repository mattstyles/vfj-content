# Speed up working with arrays

This is an old tip, but still a good one: when iterating over an array it is usually preferable to assign the subject of the current iteration to a local variable than it is to use array access multiple times.

I’m still a little [old school](http://www.urbandictionary.com/define.php?term=old%20school) and try to limit the number of local variables but there are times when doing so offers a number of benefits.

So, if you are still doing something like this:

```javascript
var i = 0;
    item = null;
    array = [ … ];

for ( i = 0; i < array.length; i = i + 1 ) {
  access array[ i ] multiple times
}
```

Then you might want to consider adding one simple line to your code to assign to a local variable and changing a few references to then use that local variable:

```javascript
var i = 0;
    item = null;
    array = [ … ];

for ( i = 0; i < array.length; i = i + 1 ) {
  item = array[ i ]
  access item multiple times
}
```

The efficiency benefit is of some importance\[[1](http://jsperf.com/local-variable-or-array-lookup)\] but there are other benefits too.

The first extra benefit is readability.  If your `for` loop spans multiple lines (it could, with comments, reach many many lines) and using the subject of the iteration (i.e. `item`) seems more intuitive (and is likely less error prone as there is less syntax to type correctly) than remembering to access the array which contains the subject using the `index` of the iteration.

Another benefit is reducing the risk of mutating the array with an errant declaration.  The risk of _accidentally_ assigning something else to `array[ i ]` should not be casually dismissed, particularly when working in a team, as it’s effects could potentially be far reaching.  

You may have written your tests, written your code, passed the tests and not even realised that you’ve inadvertently mutated the array.  Another developer then works using the array in some other part of the project and wonders why their fix/feature isn’t behaving as expected.  If there is some DOM manipulation occurring, or some responses to interactive events, then it isn’t always easy to write comprehensive tests and this sort of bug can be very difficult to track down.

Sure, you could argue for better and more efficient test cases to reduce the risk of introducing bugs in other places, and you could also argue for better division and delineation of code so that data structures are more carefully accessed, but using a local variable as a convention makes these more complex steps less important for solving this problem which means that code organisation can be optimised for making your project _better_ rather than primarily to make it more maintainable.

---

While we’re on the subject of optimisations to arrays it is worth noting that there are other array iteration methods than using a `for` loop that are generally more efficient.  The simplest when performing simple iteration over an array is using a `while` loop.  

Rather than go into too much detail it’s clearer just to run some tests on [jsperf](http://jsperf.com/fors-vs-while/58).  

This very low level optimisation might not seem particularly worthwhile, especially when your looping code may only consist of a few lines and few lookups but the other benefits make it worth considering.  Plus, even if your primary market right now are power users with high-end machines you never know where your code might end up and taking a simple and quick step shows that you are at least aware of alternate possibilities for uses for your code.

### Links

* [Variable vs Array lookup jsperf](http://jsperf.com/local-variable-or-array-lookup)

* [For loop vs While loop](http://jsperf.com/fors-vs-while/58)

* [Speed tips from Nikolas Zakas - video](http://www.youtube.com/watch?v=mHtdZgou0qU)

* [Javascript Performance Boosts - Jon Raasch](http://jonraasch.com/blog/10-javascript-performance-boosting-tips-from-nicholas-zakas)

* [Coderwall Protip](https://coderwall.com/p/k2olzq)

---

Want to discuss this article?  Best idea is to bug me/slaughter me publicly [@veryfizzyjelly](https://twitter.com/veryfizzyjelly)

---

Posted in [Coding](../"coding") on June 8th 2013.  _JavaScript_, _Arrays_, _Optimisation_