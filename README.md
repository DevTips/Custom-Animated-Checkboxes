Custom Animated Checkboxes
==========================

You should watch the [20min video tutorial on YouTube!](http://youtu.be/oh2JLo2yxCM)

---

**HTML Markup**

```
<form>
  
  <h5>Custom Checkboxes</h5>
  
  <label>
  
    <!-- Keep the input inside the label -->
    <input type="checkbox">
    
    <!-- make sure the .label-text is right next to the input-->
    <span class="label-text">Item One</span>
    
  </label>
  
  <label>
    <input type="checkbox" disabled>
    <span class="label-text">Item Two</span>
  </label>
  
  <label>
    <input type="checkbox" disabled>
    <span class="label-text">Item Three</span>
  </label>

</form>
```


**SASS Styles**
```
// Import FontAwesome
@import "https://maxcdn.bootstrapcdn.com/font-awesome/4.2.0/css/font-awesome.min.css"

label
  cursor: pointer
  color: #666
  
  // Remove the default checkbox
  input[type="checkbox"] 
    display: none
    
    // Insert the new checkbox from FontAwesome
    + .label-text:before
      content: "\f096"
      font-family: "FontAwesome"
      speak: none
      font-style: normal
      font-weight: normal
      font-variant: normal
      text-transform: none
      line-height: 1
      -webkit-font-smoothing: antialiased
      width: 1em
      display: inline-block
      margin-right: 5px
    
    // When the checkbox is checked...
    &:checked + .label-text:before
      content: "\f14a"
      color: #06a3e9
      +animation(tick 180ms ease-in)
    
    // When the checkbox is disabled...
    &:disabled + .label-text
      color: #aaa
      
      &:before
        content: "\f0c8"
        color: #ccc
        

// Bounce the checked checkbox
+keyframes(tick)
  0%
    +transform(scale(0))
  
  90%
    +transform(scale(1.4))
  
  100%
    +transform(scale(1))
  
```
