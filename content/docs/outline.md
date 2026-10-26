+++
title = "Carbide"
+++

# Carbide
Welcome to Carbide!

Carbide is a Rust GUI framework, for easily making desktop GUI applications, with focus on performance, customizeability and ...

You are currently reading the framework documentation. Our aim is to explain the different aspects of the framework, and allowing you to easily look up examples and gain insight into the decisions and use cases of the different provided features.

If you are new to Carbide, we recommend visiting [Getting Started](TODO). Otherwise you can take a look at the extensive list of [Examples](TODO).

## Features
TODO

## Developer experience
The aim is for the framework to require as little upfront configuration as possible, while allowing you to customize. It should be as easy as creating a new rust project, adding the latest Carbide crate to the `cargo.toml` and writing `cargo run`.

To reach this goal, we have chosen an opinionated set of defaults, include a set of customizable control widgets with a set of default styles, layout widgets, and a default rendering backend. But the framework allows overriding defaults, styles and allows implementing custom layout widgets, giving you the power to make the application your own.

We have done a lot of iteration on the api's, and how to create an application using the framework. We have taken a lot of inspiration from related UI frameworks in rust, while also adapting concepts from other crates, and frameworks in other languages.

## Performance
Performance is an important metric, but is still work in progress. At the moment, we have focused more on making design desitions that makes it easy to build applications, and providing the correct abstractions allowing to tweak framework internals, hopefully without requiring major api changes. 

## License
TODO