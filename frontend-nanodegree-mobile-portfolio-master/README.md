# Website Performance Optimization portfolio project

## Link to my optimized webpage: https://ckprogrammer.github.io/WebsiteOptimization/frontend-nanodegree-mobile-portfolio-master/index.html

This is the Project Website Optimizations on [Udacity's Front End Web Developer Program](https://eu.udacity.com/course/front-end-web-developer-nanodegree--nd001).


In this project I had to optimize the portfolio, by improving performance-related issues.

This optimized webpage ([index.html](https://ckprogrammer.github.io/WebsiteOptimization/frontend-nanodegree-mobile-portfolio-master/index.html)) has a ```PageSpeed``` score of 91.

## Downloading this application
1. Click on the ```Clone or Download``` button at the top of the github page.
2. Click ```Download Zip```.
3. Double click on the Downloaded zip-file in your downloads on your computer.
4. Open the index.html file on your browser.
5. You should be ready to go!

## Optimizations I made to ```index.html```
* removed any extra spaces
* compressed images (using this website: http://compressimage.toolur.com/)
* inlined css
* async javascript
* included ```media='print'``` for the print stylesheet link.
* I removed the google fonts styles link.

## Optimizations I made to ```views/js/main.js``` (pizza.html)
* This is what I changed to make the pizza sizes change faster:
```
  function changePizzaSizes(size) {
  var elementsOfPizza = document.querySelectorAll(".randomPizzaContainer");
  var dx = determineDx(elementsOfPizza[0.0], size);
  var newwidth = (elementsOfPizza[0.0].offsetWidth + dx) + 'px';
  for (var n = 0.0; n < elementsOfPizza.length; n++) {
    elementsOfPizza[n].style.width = newwidth;
  }
}
```
I did this, so that I store randomPizzaContainer in elementsOfPizza instead of re-running it many times.

*
```
var items = document.querySelectorAll('.mover');
var scrollY = document.documentElement.scrollY || document.body.scrollTop;
for (var i = 0; i < items.length; i++) {
  // document.body.scrollTop is no longer supported in Chrome. This is why I changed the ScrollTop to ScrollY.
  var phase = Math.sin((scrollY / 1250) + (i % 5));
  items[i].style.left = items[i].basicLeft + 100 * phase + 'px';
}
```

I changed the ScrollTop to ScrollY in chrome. I researched using this link: https://stackoverflow.com/questions/20514596/document-documentelement-scrolltop-return-value-differs-in-chrome

* Here, I changed from querySelector to getElementById because it is faster. I also moved the DOM call outside the for statement to save it into a local variable, which I have done with movingPizzas.

```
document.addEventListener('DOMContentLoaded', function() {
  var cols = 8;
  var s = 256;
  var movingPizzas = document.getElementById('movingPizzas1');  //Here, I changed from querySelector to getElementById because it is faster. I also moved the DOM call outside the for statement to save it into a local variable, which I have done up here.
  for (var i = 0; i < 40; i++) {
    var elem = document.createElement('img');
    elem.className = 'mover';
    elem.src = "images/pizza.png";
    elem.style.height = "100px";
    elem.style.width = "73.333px";
    elem.basicLeft = (i % cols) * s;
    elem.style.top = (Math.floor(i / cols) * s) + 'px';
    movingPizzas.appendChild(elem);
  }
  ```

### Final Comment
I shared my work with my sister Amelia Krafft who is also right now working on the Udacity's Frontend Project. This is why we could have some similarities in our code.
