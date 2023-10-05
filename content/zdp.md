+++
title = "Zig Design Patterns"
date = 2023-09-14

[taxonomies]
categories = ["blog"]
tags = ["zig", "swe"]
+++

Patterns I've seen in the Zig standard library and on the Zig News forum.

<!-- more -->

* [Traits](https://github.com/ziglang/zig/blob/0.11.0/lib/std/meta/trait.zig#L10)

* [Closure](https://github.com/ziglang/zig/blob/0.11.0/lib/std/Thread/Pool.zig#L86)

* [Context](https://github.com/ziglang/zig/blob/0.11.0/lib/std/hash_map.zig#L133)

* [Decorator](https://zig.news/xq/cool-zig-patterns-configuration-parameters-591a)

* [Arena allocator](https://github.com/ziglang/zig/blob/0.11.0/lib/std/heap/arena_allocator.zig#L8)

* [Struct of arrays](https://zig.news/andrewrk/multi-object-for-loops-data-oriented-design-41ob)

* [Custom type format](https://github.com/ziglang/zig/blob/0.11.0/lib/std/Uri.zig#L209)

* [WaitGroup + ThreadPool](https://github.com/ziglang/zig/blob/0.11.0/lib/build_runner.zig#L772)

* [Anonymous struct coercions](https://zig.news/xq/cool-zig-patterns-305o)

* [Named (optional) arguments](https://github.com/ziglang/zig/blob/0.11.0/lib/std/fmt.zig#L22)

* [Comptime string intern pool](https://zig.news/xq/cool-zig-patterns-comptime-string-interning-3558)

* [Static dispatch (tagged union)](https://zig.news/kristoff/easy-interfaces-with-zig-0100-2hc5)

* [Dynamic dispatch (fat pointer)](https://github.com/ziglang/zig/blob/0.11.0/lib/std/mem/Allocator.zig#L14)
