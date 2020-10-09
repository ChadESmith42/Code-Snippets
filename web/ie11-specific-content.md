# Displaying IE11 Specific Content (or hiding content from IE11)

## Display only in IE11
Create your CSS variables.

```css
:root {
  --ie11-only: none;
  --modern-only: block;
}
```

Create a class for IE11-only and for modern-browsers-only.

```css
.ie-only {
  display: var(--ie11-only); /* IE11 ignores this rule because it can't resolve the variable. */
  border: 2px solid rgba(44, 62, 80, 1.0);
  border-radius: 8px;
  background-color: rgba(127, 140, 141,1.0);
  color: rgba(236, 240, 241, 1.0);
}
```
```css
p.modern-browsers-only {
  display: none; /* IE11 honors this rule. */
}
```

In your HTML, create your IE11 content and your modern browser content with the appropriate classes.
```html
<div class="special-offer">
  <h2>Special Offer!</h2>
  <p class="ie-only">You can earn 10% off of your next order by using this code: UPDATEBROWSER</p>
  <p class="modern-browsers-only">You can earn 20% off of your next order by using this code: EARLYADOPTER</p>
</div>
```

## Only hide from IE11
You may not have modern-browser only content. But maybe you do! So how can you hide that from IE11? Simple.

Create a class to override the previous `modern-browsers-only` class rule. Your new rule, to hide the content from IE11, will need to be lower in the file than the first rule.
```css
p.modern-browsers-only {
  display: none; /* All of the browsers will honor this rule. */
}

div.special-offer p.modern-browsers-only {
  display: var(--modern-only); /* Modern browsers will apply this rule, but IE11 will ignore it. */
}
```

This is a simple and straightforward method of displaying, or not, content specifically for IE11.
