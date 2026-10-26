+++
title = "Environment"
+++

# Environment
One of the most common structures of Carbide is the `Environment`. The `Environment` is a [scoped](TODO) dictionary of keys and values. When Carbide processes events, calculates layouts or does rendering, an `Environment` is provided to the [Widget](TODO), containing all the state that can be used while processing. This could include settings, the current theme, and custom state. Values can be added and updated in the `Environment`, and due to its lifetime and scoping rules, can be provided when processing a widgets children.

The `Environment` can contain both mutable and immutable references to a given value. Since the `Environment` contains references to its values, a [Widget](TODO) can provide contained state to its children, while still adhering to rust's strict borrowing rules.

The mechanism is also used by Carbide to provide [Manager](TODO)'s, for example allowing a widget within a window, to request the window to be closed, requesting focus, or requesting a new animation frame.

One of the most common examples of where the environment is used in Carbide is [EnvironmentColor](TODO). The environment contains an [Accent](TODO) color, which can be overridden within a [widgets children](TODO). 

## How it works
TODO

## Scoping rules
The environment contains scoped values, and allows for shadowing. Scoping follows the same shadowing rules as Rust. Scoping is on a per key basis. Only one value can be current in the environment per key. If you insert a new value into the environment with a key that is already inserted, the previous value will be shadowed by the new value.

This is for example used when defining styles for carbide controls. Suppose we have a default button style. This could be inserted at the outermost position in the environment. A specific style can be then inserted, overriding the other style, for all widgets contained in the scope of the environment. When leaving the scope, the outermost value can be accessed again. 

It is not possible to access the value from the outer environment in the inner environment.

TODO

## Custom values
TODO