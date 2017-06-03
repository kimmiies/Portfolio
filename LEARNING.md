Iteration 1
^^^^^^^^^^^^

Position Relative:
  - everything on page is by default static.
  - giving an element position: relative means that it's relative to itself/ where it sits as default
  - must add top, right, bottom, left attribute
  - also allows it to have z-index
  - ie. navbar project list line. Wanted to bring it higher than it was sitting. 2 ways:
      - margin bottom: 3px
      - position: relative, bottom: 3px

Position Absolute:
  - relative to it's closest parent with position relative (or absolute)
  - must add top, right, bottom, left attribute


Anchor links default to blue:
  - hyperlink goes blue
  - color: inherit; inherits font-colour from parent, versus default blue for link


letter-spacing
  - it's a thing!


Having page fit browser height
  - set the body to have a fixed position and added in some javascript functionality
  - My understanding. When the window experiences a resize event it will perform the autoResize function, which sets the height of the body to the innerHeight of the window
  - want content to sit flush with bottom of the page so I added height %s to header and main (relative to body)

  function autoResizeDiv(){
    document.getElementById('main').style.height = window.innerHeight +'px';
  }
  window.onresize = autoResizeDiv;
  autoResizeDiv();


Iteration 2
^^^^^^^^^^^^

TypeJS
  - downloaded script from https://github.com/mattboldt/typed.js/
  - include typed.js file in html & populated array with appropriate strings.
  * Will see if I can create an infinite loop

CSS Animations
  - bind animation to element using animation-name: property and give your animation a name
  - @keyframe animation-name property will let you specify what the current style is and the new style
  - animation properties define what happens in between
      ie. duration

Iteration 3
^^^^^^^^^^^

Media Queries with Sass
  - https://davidwalsh.name/write-media-queries-sass
  - Mixins: Groups of styles that can be reused throughout your code
  - Cleaning up the code by first defining variables to define media queries, then using the power of Sass to nest them, then writing mixins to make it easier to read :D

      $tablet-width: 768px;
      $desktop-width: 1024px;

      @mixin mobile {
        @media (max-width: #{$tablet-width - 1px}) {
          @content;
        }
      }

      body {
        font-family: 'PT Sans', sans-serif;
        @include mobile {
          background-color: papayawhip;
        }
