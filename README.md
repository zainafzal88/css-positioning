# css-positioning
This repository contains code and explanation of CSS position values, static, absolute, relative, fixed and sticky

## Requirements
* Basic HTML knowledge
* Basic CSS knowledge excluding `position` property
* A text editor 
* Local web server

## Getting Started
1.  Download or clone the repository
2.  Open it in your favourite text editor
3.  Delete all the code in  `styles.css` so it looks like

```
.static {
  background-color: rgb(190, 121, 255);
}
.parent {
  background-color: red;
}
.child-one {
  background-color: darkgreen;
}
.child-two {
  background-color: yellow;
}
.child-three {
  background-color: orchid;
}
```
4. Open `index.html` and make the body look like
```
<body>
        <h2>Positioning in CSS</h2>
        <div class="parent">
            Parent Div
            <div class="">Div 1</div>
            <div class="">Div 2</div>
            <div class="">Div 3</div>
        </div>
    </body>
```
## Running Locally

### Static
This is selected by default. This is the only value that doesn't need properties, top, bottom, right and left. If you see any element that doesn't have a position value, just assume, it has `static` in its CSS invisibly.

Add the following code to `.static` in `styles.css`

```
.static {
    position: static;
    border: 2px solid;
    background-color: rgb(190, 121, 255);
}
```
Apply the `static` class on `Div 1`  in your `index.html`, It should look like:

```
<div class="static">Div 1</div>
<div class="">Div 2</div>
<div class="">Div 3</div>
```
Open your browser and observe the result. This demonstrates `static` positioning in CSS

### Relative
This is the same as `static` however, it needs to have either properties, top, bottom, left and right for it to work. 
It pulls the element out its original place on the page and can move it around in the way that it can hide other elements 
near it.

Represented by `position: relative;`

Replace existing code with the following for `.child-one` in `styles.css`:
```
.child-one {
    position: relative;
    background-color: darkgreen;
    left: 20px;
    top: 30px;
    color: #fff;
}
```
Replace `class="static"` with `class="child-one"` for `Div1` in `index.html`
```
<div class="child-one">Div 1</div>
```
As you should've seen in your browser, `Div 1` is overlapping `Div 2` and `Div 3` which clearly shows that `Div 1` is no 
longer "embedded" in the page and it's free to move without caring how it effects other elements in the page.

### Absolute
Positions the element next to its nearest parent. It doesn't care about other elements. It will hide other elements behind 
it if they try to effect it but it won't be effected. It's written as `position: absolute`.

Replace `.child-one` CSS with the below code:

```
.child-one {
    position: absolute;
    top: 10px;
    background-color: darkgreen;
    color: #fff;
}
```
By applying property `top:10px` on absolute position observe how the element goes relative to the viewport(browser). To avoid the above behaviour, we can simple apply `position: relative` to its nearest parent.
```
.parent {
    background-color: red;
    position: relative;
}
.child-one {
    position: absolute;
    top: 10px;
    background-color: darkgreen;
    color: #fff;
}
```

### Sticky
Positions the element in a way it's always visible to the user. What I mean by that is when `position: sticky` is applied 
to an element at the start of the page (for example), initally it stays in its original place and when the users scrolls 
through that area, that element stays fixed on the top so, even if the user has scrolled down, he can still view that element.

`sticky` position is the combination of `relative` and `fixed`. Remember the above concept, `relative` applies when element 
initally stays in its original place whereas `fixed` applies when the users scrolls through that area, that element stays 
fixed on the top so, even if the user has scrolled down, he can still view that element. 

You can view this [example](https://www.w3schools.com/css/css_positioning.asp)

CSS code would look like:

```
.child-two {
    background-color: yellow;
    position:sticky;
    top:0;
}
```
### Fixed
Positions the element next to the viewport (browser) and "glues" it in one place even when the user scrolls. 
Either of the properties, top, left, right and bottom are compulsory to be user with this. Otherwise, it won't work

Add the below code to `.child-two` in `styles.css`
```
.child-two {
    background-color: yellow;
    position: fixed;
    top: 0;
    left: 0;
}
```


