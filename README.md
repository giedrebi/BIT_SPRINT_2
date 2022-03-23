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
To made sidebar into two sections, I added these two tags into above tag:
1. ```<div class="sidebar_header"></div>```
2. ``` <ul></ul>```

In `sidebar_header` I inserted `img` and `a` tags:
```
<div class="sidebar_header">
    <img id="portrait" src="../images/Giedre Bielske.jpg" alt="Giedre Bielske photo">
    <a href="../index.html">Web developer</a>
</div>
```
To style sidebar I added these selectors in style.css file:
```
.sidebar {
    position: fixed;
    left: -12rem;
    width: 12rem;
    height: 100%;
    z-index: 1;
}
.sidebar_header {
    font-size: 1rem;
    color: white;
    padding: 1rem 0;
    line-height: 2rem;
    text-align: center;
}
.sidebar_header a:hover {
    font-size: 1.2rem;
}
```
*Images, gifs and video you will find in folder images*

In an unordered list ``` <ul></ul>``` I inserted `li` tags to navigate in my website:
```
<ul>
    <li>
        <a href="../pages/about.html"><i class="far fa-user"></i>ABOUT ME</a>
    </li>
    <li>
        <a href="../pages/projects.html"><i class="fas fa-laptop-code"></i>PROJECTS</a>
    </li>
    <li>
        <a href="../pages/contact.html"><i class="fas fa-phone-square-alt"></i>CONTACT</a>
    </li>
</ul>
```
To style list (`ul`,`li`and`a`) I added these selectors in style.css file:
```
a {
    display: block;
    color: white;
    transition: 0.5s;
    font-size: 1rem;
    text-align: center;
}
li:hover a {
    font-size: 1.2rem;
}
.sidebar a {
    line-height: 3rem;
}
```
### 3. Font asewome icons

First I added `@import url` into style.css folder:
```
@import url("https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css");
```
Then I take few icons from https://fontawesome.com/icons and added in html file into buttons tag `label`, sidebar and footer lists tag `ul>li`. For example:
Copy `i` tag and insert it to buttons in `label` tag:
```
<label for="sidebar_checkbox">
    <i class="fas fa-bars" id="bar_btn"></i>
    <i class="fas fa-times" id="cancel_btn"></i>
</label>
```
To style `i` tag I added this selector to style.css file:
```
i {
    margin-right: 0.5rem;
}
```
### 4. Two columns layout
In `section` I added identical `div` tags by using `class="row"`. Into row I added `div` by using `class="box"`:
```
<section>
    <div class="row">
        <div class="box name welcome">
            <h1>Hi,</h1>
            <h1>I'm Giedre,</h1>
            <h1>Web developer</h1>
            <p>HTML / CSS</p>
        </div>
    </div>
    <div class="row"></div>
</section>
```
And to style `row` and `box` I added these selectors in style.css file:
```
.row {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    margin-left: 14rem;
}
.box {
    width: 40%;
    padding: 1rem;
    margin: 2rem;
    text-align: center;
    color: white;
    text-shadow: 1px 1px 4px white;
    background: #410541d5;
    box-shadow: 0 8px 32px 0 rgba( 31, 38, 135, 0.37 );
    backdrop-filter: blur( 4px );
    -webkit-backdrop-filter: blur( 4px );
    border-radius: 50px;
}
.box > h1  {
    font-size: 3rem;
}
.box > h2 {
    margin-bottom: 1rem;
}
.box > p {
    font-size: 1rem;
    margin: 1rem 0;
}
```
### 5. Two columns footer
In `footer` I added two columns navigation for my website by using `class="column"`:
```
<div class="footer_nav">
    <ul class="column">
        <li>
            <a href="index.html"><i class="fas fa-home"></i>HOME</a>
        </li>
        <li>
            <a href="pages/about.html"><i class="far fa-user"></i>ABOUT ME</a>
        </li>
    </ul>
    <ul class="column">
        <li>
            <a href="pages/projects.html"><i class="fas fa-laptop-code"></i>PROJECTS</a>
        </li>
        <li>
            <a href="pages/contact.html"><i class="fas fa-phone-square-alt"></i>CONTACT</a>
        </li> 
    </ul>
</div>
```
*How to add font awesome (`i` tags) you will find in section 3.*

To style footer I added these selectors in style.css file:
```
section {
    padding-bottom: 7rem;
}
footer {
    position: absolute;
    bottom: 0;
    width: 100%;
    background: #410541d5;
    text-shadow: 1px 1px 4px white;
    box-shadow: 0 8px 32px 0 rgba( 31, 38, 135, 0.37 );
    backdrop-filter: blur( 2px );
    -webkit-backdrop-filter: blur( 2px );
    color: white;
}
.footer_nav {
    display: flex;
    padding: 1rem 0;
}
.column {
    flex: 50%;
}
.column a {
    line-height: 2rem;
}
```
### 6. Animation
I added animation to one of`div .box`to change text color.
In html file I added `class="name"`:
```
<div class="box __name__ welcome">
    <h1>Hi,</h1>
    <h1>I'm Giedre,</h1>
    <h1>Web developer</h1>
    <p>HTML / CSS</p>
</div>
```
