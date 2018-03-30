# Website Performance Optimization portfolio project

##Link to my optimized webpage: https://ckprogrammer.github.io/WebsiteOptimization/frontend-nanodegree-mobile-portfolio-master/index.html

This is the Project Website Optimizations on [Udacity's Front End Web Developer Program](https://eu.udacity.com/course/front-end-web-developer-nanodegree--nd001).


In this project I had to optimize the portfolio, by improving performance-related issues.

This optimized webpage ([index.html](https://ckprogrammer.github.io/WebsiteOptimization/frontend-nanodegree-mobile-portfolio-master/index.html)) has a ```PageSpeed``` score of 91.

## Downloading this application
1. Click on the ```Clone or Download``` button at the top of the github page.
2. Click ```Download Zip```.
3. Double click on the Downloaded zip-file in your downloads on your computer.
4. Open the index.html file on your browser.
5. You should be ready to go!

##Optimizations I made to ```index.html```
* removed any extra spaces
* compressed images (using this website: http://compressimage.toolur.com/)
* inlined css
* async javascript
* included ```media='print'``` for the print stylesheet link.
* I removed the google fonts styles link.

##Optimizations I made to ```views/js/main.js``` (pizza.html)
* This is what I changed to make the pizza sizes change faster:
  function changePizzaSizes(size) {
  var elementsOfPizza = document.querySelectorAll(".randomPizzaContainer");
  var dx = determineDx(elementsOfPizza[0.0], size);
  var newwidth = (elementsOfPizza[0.0].offsetWidth + dx) + 'px';
  for (var n = 0.0; n < elementsOfPizza.length; n++) {
    elementsOfPizza[n].style.width = newwidth;
  }
}
* To make the scrolling of the page faster, I changed all of the ```ScrollTop``` to ```ScrollY``` because ```ScrollTop``` is no longer accepted in chrome. I researched using this link: https://stackoverflow.com/questions/20514596/document-documentelement-scrolltop-return-value-differs-in-chrome
