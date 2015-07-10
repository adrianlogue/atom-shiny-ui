# Shiny UI Theme

Updated for Atom 1.0!

Shiny UI is a bright, fresh theme. All elements are slightly flattened, lightened, embiggened and Helvetica-ized.

![Shiny UI](http://adrianlogue.github.io/images/shiny-ui-v0.32.0.png "Shiny UI")

I recommend matching Shiny UI with the Fizzy Syntax theme by Joel Glovier (https://atom.io/themes/fizzy)

This theme can be activated by going to the _Themes_ section in the Settings view (`cmd-,`)
and selecting it from the _UI Themes_ drop-down menu.


## Horizontal scrolling in Tree-View

In the initial releases of Shiny UI, I set it up so that the Tree View pane automatically resized to fit it's contents and thus eliminated ever having horizontal scrolling in the Tree View. This was very much a personal preference which I recognise isn't for everyone, and it had the downside of making the Tree View pretty massive if you had a particularly long filename or deeply nested folders. So I've disabled it by merging a pull request generously supplied by Mateus Dalto Piveta (https://github.com/mdalpi).

If (like me) you prefer the old auto-resizing and lack of horizontal scrolling in the Tree View then you can re-enable it by putting the following into your styles.less:

```less
.tree-view-resizer {
    width: auto !important;

    .tree-view-resize-handle {
        cursor: default;
    }
}
```

This should work in most UI Themes by the way.

Furthermore to re-instate the rounded corners and padding around the selected items in the Tree View, add this to your styles.less:

```less
@import "ui-variables";

.tree-view,
.tree-view:focus {
    .selected:before {
        display: block !important;
        left: 6px;
        right: 8px;
        border-radius: @component-border-radius;
    }
}
```
