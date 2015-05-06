# wrapperElement
```html
<wrap fill='height' distribute='center-y right'>
  <span>Some text</span>
  <img src='image.png'>
  <input type='text' placeholder='type here'>
</wrap>
```

`<wrap>` is a superabstract non-invasive CSS layout building block. 

It's very compatible (isn't flexbox) and by design keeps a small yet highly reusable set of features. It's intention is to simplify common CSS core prototyping patterns, like aligning icons with text or input fields and positioning itself and its contents.  

The proverbial `.wrapper` gone wild, late to the table but now here to stay anyway!

__Should I use flebox instead?__  
Probably, if you can. But sometimes you can’t, or maybe you don't want to.. you hipster.  

## Usage
Just add `<link href='wrap.css' rel='stylesheet' type='text/css'>` to your document.
###Pure element

```html
<wrap fill='height' distribute='center-x right'>
```
###W3C valid element

```html
<wrap-per data-align='float' data-debug>
```
###CSS classes

```html
<div class='wrap wrap-fill--width wrap-clear'>
```  

## Attributes
### fill
By default, `<wrap>` is an `inline-block` element, so it's as wide and as high as it's content.
```html
<wrap fill='width|height|both|float'>
```  

`width` - auto-fills available parent width  
`height` - fills 100% parent height  
`both` - both of the above  
`float` - fills remaining horizontal space after a floated element

### align
Positions itself inline, relatively to parent or fixed on screen.
```html
<wrap align='left|right|center|center-parent|center-screen'>
```  

`left` `right` - floats  
`center` - inline relative center (uses transform)   
`abs-center` - bullseye center of first relative parent (uses transform)  
`fixed-center` - bullseye center fixed of screen (uses transform)

### distribute
Sets alignment for its direct child elements, no value defaults to `left`. Multiple space-separated properties can be used.
```html
<wrap distribute='left|right|center-x|center-y|top|bottom'>
```  

`left` `right` - aligns children to sides  
`top` `bottom` - distributes all children to top | bottom border  
`center-x` - centers all children vertically relative to own height  
`center-y` - centers all children horizontally relative to own width  


### clear
Clears all preceding floats.
```
<wrap clear>
```  

### debug
Displays borders around the element and a little fancy flag. Also usable by setting a `.debug` class on any parent element.
```
<wrap debug>
```
