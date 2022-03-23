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
##### Open and close buttons
To open and close sidebar navigation, I added `input` and `label` elements to html file:
```
<input type="checkbox" id="sidebar_checkbox" />
<label for="sidebar_checkbox">
    <i class="fas fa-bars" id="bar_btn"></i>
    <i class="fas fa-times" id="cancel_btn"></i>
</label>
```
*How to add font awesome you will find in section 3.*

