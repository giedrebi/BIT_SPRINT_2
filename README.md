# BIT_SPRINT_2

Website url: https://giedrebi.github.io/BIT_SPRINT_2/ 

## TASK: create CV/portfolio website with three pages

In this project you will find:
1. video background;
2. left sidebar;
3. font awesome icons;
4. two columns layout;
5. two columns footer;
6. animation;
7. gifs;
8. contact form;
9. @media responsive website;
10. `meta` tags.


All code was made with HTML and CSS.

First, in style.css file I added `body` and `*` selectors:
```
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Montserrat', sans-serif;
    list-style: none;
    text-decoration: none;
}
body {
    position: relative;
    min-height: 100vh;
}
```
The font for this website I chose from google fonts, and added url `@import` in style.css file:
```
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');
```
### 1. Video background

To make video as background, I needed to add `video` tag to html file in `body` section (in every page of website):
```
<video>
    <source src="../images/Abstract.mp4" type="video/mp4">
</video>
```
I wanted that video would start automaticaly, with no sound, and would repeat again and again, so I added few atributtes to `video` tag:
```
<video autoplay muted loop>
    <source src="../images/Abstract.mp4" type="video/mp4">
</video>
```
In style.css file I added few declarations for selector `video`:
```
video {
    position: fixed;
    right: 0;
    bottom: 0;
    min-width: 100%;
    min-height: 100%;
}
```
### 2. Left sidebar
#### Open and close buttons
To open and close sidebar navigation, I added `input` and `label` elements to html file:
```
<input type="checkbox" id="sidebar_checkbox" />
<label for="sidebar_checkbox">
    <i class="fas fa-bars" id="bar_btn"></i>
    <i class="fas fa-times" id="cancel_btn"></i>
</label>
```
*How to add font awesome you will find in section 3.*

To style those buttons I added these selectors in style.css file:
```
#bar_btn , #cancel_btn  {
    position: absolute;
    cursor: pointer;
    font-size: 2rem;
    top: 1.5rem;
    padding: 6px 12px;
    color: white;
    text-shadow: 1px 1px 4px white;
    background: #410541d5;
    box-shadow: 0 8px 32px 0 rgba( 31, 38, 135, 0.37 );
    backdrop-filter: blur( 4px );
    -webkit-backdrop-filter: blur( 4px );
    border-radius: 50px;
}
#bar_btn {
    left: 3rem;
    transition: all 0.5s;
    font-size: 1.5rem;
}
#cancel_btn {
    left: -3rem;
    z-index: 2;
    transition: all 1s;
    top: 2rem;
    font-size: 1rem;
}
#sidebar_checkbox {
    display: none;
}
#sidebar_checkbox:checked ~ .sidebar {
    left: 0;
    transition: all 1s;
}
#sidebar_checkbox:not(checked) ~ .sidebar {
    transition: all 1s;
}
#sidebar_checkbox:checked ~ label #bar_btn {
    left: 0;
    opacity: 0;
    pointer-events: none;
}
#sidebar_checkbox:checked ~ label #cancel_btn {
    left: 13rem;
}
```
#### Left sidebar 
To create sidebar, I added `div` tag to html file:
```
 <div class="sidebar"></div>
```
I made sidebar into two sections:
1. ```<div class="sidebar_header"></div>```
