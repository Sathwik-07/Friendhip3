# responsive-navbar-js

Create a responsive navbar with only Javascript, CSS and HTML

# THE LOGIC

This concept relies mostly on css and js first look at the at the structure of the css and the html file but the main logic are as follows

# CSS

```css
/* THE LOGIC */

/* First: Hide the show icon by default */
.social-icons {
  display: none;
}

/* 2. Hide the links if it's height is not enough to accommodate. That's how html works, if it's height is not enough it won't show, so as the user reduces the size of the window it decreases the height of the parent of the link item but the problem is that if you don't give it overflow:hidden it will jump to next line so hidden:0 and overflow:hidden will hide an html parent container */

/* By default let's hide this */
.links {
  height: 0;
  overflow: hidden;
  transition: all 0.3s linear;
}

/* This is the class we will add to the links by js to show the links again because it has a height */
.show-links {
  height: auto;
  transition: all 0.3s linear;
}

/* Implementations */
@media screen and (min-width: 800px) {
  .nav-center {
    max-width: 1170px;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 1rem;
  }
  .nav-header {
    padding: 0;
  }
  /* Hide toggle on the large screen */
  .nav-toggle {
    display: none;
  }
  /* Give the links a height to show on a large screen */
  .links {
    height: auto;
    display: flex;
  }
  .links a {
    padding: 0;
    margin: 0 0.5rem;
    color: antiquewhite;
  }
  .links a:hover {
    padding: 0;
    background: transparent;
    transform: rotate(10deg);
    color: #493b2a;
  }
  /* Show the social icons on large screen */
  .social-icons {
    display: flex;
  }
  .social-icons a {
    margin: 0 0.5rem;
    color: wheat;
    transition: all 0.3s linear;
  }
  .social-icons a:hover {
    color: var(--clr-primary-7);
  }
}
```

# Javascript

```js
// classList - shows/gets all classes
const navToggle = document.querySelector('.nav-toggle');
const links = document.querySelector('.links');

// contains - checks classList for specific class
// add - add class
// remove - remove class
// toggle - toggles class

navToggle.addEventListener('click', () => {
  //   console.log(links.classList);
  //   console.log(links.classList.contains('links'));
  //   if (links.classList.contains('show-links')) {
  //     links.classList.remove('show-links');
  //   } else {
  //     links.classList.add('show-links');
  //   }

  //OR
  links.classList.toggle('show-links');
});
```
