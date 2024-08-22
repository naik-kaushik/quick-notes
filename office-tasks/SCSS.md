
#### Why SCSS?
- Because CSS is not enough.
- SCSS uses better syntaxes.
- less code , no repetition.

#### Differences between CSS and SCSS

styling in CSS:

```css
nav {
  background-color:#333;
  padding:1em;
}
nav ul {
  margin:0;
  padding:0;
  list-style:none;
}
nav ul li {
  display:inline-block;
}
```

Same styling in SCSS is as follows :
```scss
nav {
  background-color:#333;
  padding:1em;
  ul {
    margin:0;
    padding:0;
    list-style:none;
    li {
      display:inline-block;
    }
  }
}
```

**Here’s the bottom line: nesting makes code more clear, organized, and concise, but be careful not to overuse it.**



#### Using _&_ in nesting

styling for `hover` effect in CSS : 
```css
button {
  background-color: #535353;
  color: #000;
}
button:hover {
  background-color: #000;
  color: #fff;
}
```

similar effects in SCSS :
```scss
button {
  background-color: #535353;
  color: #000;
  &:hover {
    background-color: #000;
    color: #fff;
  }
}
```

Other use cases of &
```scss
.some-class {
  &:hover {
    /* when hovered */
  }
  &:focus {
    /* when focused */
  }
  & > button {
    /* selector equls to .some-class > button */
  }
  &-cool {
    /*** Notice this! ****/
    // selects .some-class-cool elements
  }
}
```

#### Variables in SCSS :

Variable declaration:

```scss
$my-font: Nunito, sans-serif;
$my-font-color: #ffd969;
$content-width: 660px;
```

Variable usage:

```scss
body {
  font-family: $my-font;
  color: $my-font-color;
  content {
    width: $content-width;
  }
}
```

#### Mixins in SCSS :

A mixin is a group of CSS declarations that can be reused. The syntax is similar to functions in JavaScript.

Here’s how to use mixins to position elements to absolute center:

```scss
@mixin absolute-center() {
  position:absolute;
  left:50%;
  top:50%;
  transform:translate(-50%,-50%);
}
.element-1 {
  @include absolute-center();
}
.element-2 {
  @include absolute-center();
  color:blue;
}
```

Below is an example of how to use arguments in mixins.

```scss
@mixin square($size) {
  width:$size;
  height:$size;
}
div {
  @include square(60px);
  background-color:#000;
}
```

