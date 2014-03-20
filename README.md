style-css
=========

Styleguide for writing CSS at DIY

## Less

While we have all the functionality of less we should avoid using more advanced features if there isn't a 
good reason to use them.

### Nesting

Nesting is chill, but don't nest deeper than `3` levels – it's a sign of overcomplexity. 
If you find yourself doing this take a step back to reconsider how the css you're working 
on can be rewritten/simplified.

```less
// not chill
.this {
    .is {
        .NOT {
            .ok {
            
            }
        }
    }
}

// chill
.this {
    .is {
        .ok {
        
        }
    }
}
```
