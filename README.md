style-css
=========

Styleguide for writing CSS at DIY

## Spacing

No lines should exceed `80` characters (makes it easier to code on laptops).

Properties and selectors should rest on new lines unless they're brief enough.

Selectors should be followed by a space and opening bracket.

```
.my-selector {
```

Then indent of `4` spaces for every property declaration.

```
    prop: val;
    prop2: val;
```

Then a closing bracking.

```
}
```

```css
/* not chill */
.my-selector { background: #333; color: #fff; border: 1px solid #fff; padding: 20px; }

/* chill */
.my-selector {
    background: #333;
    color: #fff;
    border: 1px solid #fff;
    padding: 20px;
}

.my-selector { color: #333 } /* pretty tiny */
```

Properties and values should be separated by a colon and one space.

```css
/* not chill */
.my-selector {
    background:#333;
    color : #fff;
}

/* chill */
.my-selector {
    background: #333;
    color: #fff;
}
```

## Organization

It helps to group properties by type.

```css
.my-selector {
    /* Positioning */
    display: block;
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    z-index;

    /* Box Properties */
    margin: 5px;
    padding: 5px;
    width: 100px;
    height: 100px;

    /* Content in Element/Typography */
    font-family: "Apex Rounded";
    color: #333;
    line-height: 1.5;

    /* Element itself/Presentation */
    background: #fafafa;
    border: 1px solid #ff9900;
}
```

Will post a full list of how to group.

The section on organization is a pretty solid start https://medium.com/coding-design/3996de35389e.

## Selectors

Almost never use IDs for selectors. In almost every case it's more beneficial to
add a class to your target and create a reusable component. Same goes for using
elements in selectors. Avoid tying your styles to actual markup as the markup
can change (say you wanna swap a `button` for an `a` you'd only have to update
the markup and your css will work as expected).

```css
/* not chill */
#my-element { ... }
span.subtitle { ... }

/* chill */
.my-element { ... }
.subtitle { ... }
```

## Vendor Prefixes

Don't add 'em! Define the property as spec'd and prefixes will be added as a
part of our frontend build chain.

## Less

While we have all the functionality of less we should avoid using more advanced features if there isn't a
good reason to use them.

### Nesting

Nesting is chill, but don't nest deeper than `3` levels – it's a sign of overcomplexity.
If you find yourself doing this take a step back to reconsider how the css you're working
on can be rewritten/simplified.

```less
/* not chill */
.this {
    .is {
        .NOT {
            .ok { }
        }
    }
}

/* chill */
.this {
    .is {
        .ok { }
    }
}
```

### Functions

Unless you're generating some gnarly css that needs loops or scoping avoid using
functions.
