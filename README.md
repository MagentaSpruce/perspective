# perspective
Part of daily clone project.
30 day JS Projects challenge

This project creates 3d background with layering and a side navigation bar.

This project helped me to learn and understand better:
1) Inline style animations
2)  transform-style: preserve-3d 
3)  Creating elements with ::before and ::after pseudo selectors
4)  Transform origin
5)  Animations
6)  Perspective
7)  Translate(Z)
8)  CSS selecting


This project is not slated for any improvements and has no known bugs in need of fixing. 

A simple walkthrough and explanation of the interesting code is beow:

To create 3d space for required elements this was very useful.
```CSS
transform-style: preserve-3d;
```

Creating elements for the navbar using ::before and ::after pseudo selectors.
```CSS
.bar {
  width: 1.9rem;
  height: 1.5px;
  border-radius: 2px;
  background-color: #fff;
  transition: 0.5s;
  position: relative;
}

.bar::before,
.bar::after {
  content: "";
  position: absolute;
  width: inherit;
  height: inherit;
  background-color: #eee;
  transition: 0.5s;
}

.bar::before {
  transform: translateY(-9px);
}

.bar::after {
  transform: translateY(9px);
}
```

The effect of creating the layered overlay is done by doing this to the desired elements: 
```CSS
transform: perspective(1300px) rotateY(20deg) translateZ(310px) scale(0.5);
```

Perspective dictates and translate(Z) are most responsible for the effect.

Using inline styling for animations:
```HTML
 <li><a href="#" style="--i: 0.05s">Home</a></li>
          <li><a href="#" style="--i: 0.1s">Services</a></li>
```
```CSS
  animation: appear 0.5s forwards ease var(--i);
```
