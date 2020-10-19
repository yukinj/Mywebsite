## Basic CSS
- override style:   class < subsequent class < id < inline style < !important
- color representation:  1.hex code 2. rgb(0,0,0)

- create custome css varible: 
```css
--custome-varible: gray
```
- use customize css by use var()
- to improve browser compatibility, add additional repeated property right before targeted property
- css inheritance
```
:root
```
child element can override the value from parent varible 
- use media query to change variable 
```css
  @media (max-width: 350px) {
    :root {
      /* Only change code below this line */
        --penguin-size: 200px;
        --penguin-skin: black;
      /* Only change code above this line */
    }
  }
```
right before we have set value for these properties in :root selector

### Visual Design
1. text-align:
 justify; center; right; left
absolute value(px); relative length(em); percantage(%)
2. make text bold:``` <strong> ```tag 
3. underline text: ```<u>``` tag
4. italicize text: (1)```<em>```; (2)css style ```font-style:italic```
5. strikethrough: (1)```<s>```(2) css style ```text-decoration:line-through```
6. create horizontal line: ```<hr>```. note it's a self closing tag 
7. background-color: rgba(255,255,255,1)
```
rgba stands for:
  r = red  range(0,255)
  g = green
  b = blue
  a = alpha/level of opacity, range(0,1)
  ```
  8. font-size 
  9. box-shaddow:  includes ```offset-x```, ```offset-y```, ```blur-radius```, ```spread-radius```, ```color```
  example:

   ```css 
   box-shadow: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23);
   ```