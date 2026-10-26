+++
title = "Overview"
+++

# Rendering Overview
Carbide is backend agnostic. It is intentionally designed to allow implementing multiple different backends, such as rendering to a window, to an image, to a pdf, and other targets.

This design decision dates back to the origin of the framework, when it was forked from conrod. Multiple backends have some advantages. For example, if some new rendering framework is implemented, such as [Vello](https://github.com/linebender/vello) that has a different implementation and focus than for example [Glow](https://github.com/grovesNL/glow) or [Wgpu](https://github.com/gfx-rs/wgpu), it is possible to switch, without needing to touch any of your application code.

To achieve this, we have designed a generic and declarative interface that allows specifying shapes, transforms and other rendering features, without specifying how they are converted to pixels and placed on the screen. The current reference implenentation is using WGPU, and to render a shape using WGPU, we need to tesselate the shape(convering the description into triangles) and sending these to the GPU, rendering using a custom shader. The specifics of how shapes are tesselated and the results are cached and split into rendering passes is up to the implementor.

The declarative interface is inspired by the canvas api from html, where you can choose to rendering using simple command such as `lineTo`, `moveTo` and `fill`.

It also comes with some drawbacks. Some rendering backends might not support all features, required to render the full application. For example specific rendering features like convolution filters and drop shadows can be complex to support efficiently.