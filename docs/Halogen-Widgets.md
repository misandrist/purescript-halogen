# Module Documentation

## Module Halogen.HTML.Widget


This module defines helper functions for working with third-party widgets.

#### `widget`

``` purescript
widget :: forall eff i s. { destroy :: s -> Node -> Eff eff Unit, update :: s -> Node -> Eff eff (Maybe Node), init :: (i -> Eff eff Unit) -> Eff eff { node :: Node, state :: s }, id :: String, name :: String } -> V.Widget eff i
```

Create a `VTree` from a third-party component (or _widget_), by providing a name, an ID, and three functions:

- An initialization function, which creates the DOM node, and receives a callback function which can
  be used to generate inputs
- An update function, which receives the previous DOM node and optionally creates a new one.
- A finalizer function, which deallocates any necessary resources when the component is removed from the DOM.

The three functions share a common piece of data of a hidden type `s`.



