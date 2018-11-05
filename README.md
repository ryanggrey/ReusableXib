# Reusable Xib
This project demos how to create and reuse a view via a xib file:
1. Create `XibView` component to load a named xib file and layout. The name of the xib should/can be set via an `IBInspectable` property. See [XibView.swift](./ReusableXib/XibView.swift) for example.
1. Create a xib file that contains the view hierarchy to be reused.
1. Add a view to your storyboard and set its class to `XibView`. Set the name of the xib file to be loaded in the storyboard.

## Pros
- Can see rendered xib file in Interface Builder (by implementing `prepareForInterfaceBuilder`)
- Can reuse View/Layout defined in xib files

## Cons
- Cannot customise the reused view in the place of reuse. For example see [Main.storyboard](./ReusableXib/Base.lproj/Main.storyboard) and try to add a view to the header view or body view. The best you can do is add views as subviews at the same level of the `XibView`'s content view. This means we cannot use this pattern to encapsulate **layout**.