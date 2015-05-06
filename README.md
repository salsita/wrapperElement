# wrapperElement
```html
<wrap fill='height' distribute='vertical'>
  <span>Some text</span>
  <img src='image.png'>
  <input type='text' placeholder='type here'>
</wrap>
```

wrapperElement is a superabstract non-invasive CSS layout building block. 

It's very compatible (isn't flexbox) and by design keeps a small yet highly reusable set of features. It's intention is to simplify common CSS core prototyping patterns, like aligning icons with text or input fields and positioning itself and its contents.  

The proverbial `.wrapper` gone wild, late to the table but now here to stay anyway!

__Should I use flebox instead?__  
While some of the features are less straightforward to achieve in flexbox, you should.  

## Usage
Just add `<link href='wrap.css' rel='stylesheet' type='text/css'>` to your document.
###Pure element

```html
<wrap fill='height' align='center' clear>
```
###W3C valid element

```html
<wrap-per data-contents='vertical' data-debug>
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
<wrap align='left|right|center|abs-center|fixed-center'>
```  

`left` `right` - floats  
`center` - inline relative center (uses transform)  
`abs-center` - bullseye center of first relative parent (uses transform)  
`fixed-center` - bullseye center fixed of screen (uses transform)

### distribute
Sets alignment for its child elements.
```html
<wrap distribute='vertical|horizontal|top|bottom'>
```  

`vertical` - centers all children vertically relative to own height  
`horizontal` - centers all children horizontally relative to own width  
`top` - distributes all children to own top border  
`bottom` - distributes all children to own bottom border

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