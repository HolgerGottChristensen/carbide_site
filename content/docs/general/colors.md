+++
title = "Colors"
+++

# Colors
When rendering in Carbide, each shape can have a color. In Carbide, this color is specified using an enum (in `color.rs`), and can be constructed on multiple different ways. 

The most common way to create a new Color is by using its `::new_rgb()`[^1] or `::new_rgba()`[^2] methods. These will construct a RGBA color based on the different color components given as input.

Carbide has a few predefined colors. These can be used as simple debugging colors. The predefined colors are not recommended to be used, since they where migrated over when we forked Conrod in 2021, and has not been updated since.

A few other interesting ways of constructing a color exist. You can generate a random color using `::random()`[^3] method, which creates a new random color each time the method is called. You can also generate a new color based on the current time using the `::time()`[^4] method. This rotates through different hues of an HSL color based on the current time.

It is recommended, when rendering, to use [EnvironmentColor](TODO), and not use the Color type directly. This enables Carbide to apply [themeing](TODO) and other modifications to the color based on user preferences, such as lightmode, darkmode, and custom themes. It also allows custom overrides higher in the [widget tree](TODO), for example setting the [EnvironmentColor](TODO) red, to another shade, or an entirely other color.

## Color reprensentation

## EnvironmentColor

## Footnotes
[^1]: My reference
[^2]: My reference
[^3]: My reference
[^4]: My reference