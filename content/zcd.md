+++
title = "Zig Code Design"
date = 2023-09-14

[taxonomies]
types = ["list"]
tags = ["zig"]
+++

Idiomatic Zig programming patterns from the [Zig standard library](https://ziglang.org/documentation/master/std).

<!-- more -->

- ## [Trait](https://github.com/ziglang/zig/blob/0.11.0/lib/std/meta/trait.zig#L10)

- ## [Closure](https://github.com/ziglang/zig/blob/0.11.0/lib/std/Thread/Pool.zig#L86)

- ## [Context](https://github.com/ziglang/zig/blob/0.11.0/lib/std/hash_map.zig#L133)

- ## [Decorator](https://zig.news/xq/cool-zig-patterns-configuration-parameters-591a)

- ## [Diagnostics](https://github.com/ziglang/zig/blob/0.11.0/lib/std/json/scanner.zig#L195)

- ## [Generic type](https://github.com/ziglang/zig/blob/0.11.0/lib/std/hash_map.zig#L370)

- ## [Arena allocator](https://github.com/ziglang/zig/blob/0.11.0/lib/std/heap/arena_allocator.zig#L8)

- ## [Struct of arrays](https://zig.news/andrewrk/multi-object-for-loops-data-oriented-design-41ob)

- ## [Custom type format](https://github.com/ziglang/zig/blob/0.11.0/lib/std/Uri.zig#L209)

- ## [Field parent pointer](https://github.com/ziglang/zig/blob/0.11.0/lib/std/Thread/Futex.zig#L640)

- ## [WaitGroup + ThreadPool](https://github.com/ziglang/zig/blob/0.11.0/lib/build_runner.zig#L772)

- ## [File container reference](https://github.com/ziglang/zig/blob/0.11.0/lib/std/Thread.zig#L24)

- ## [Named (optional) argument](https://github.com/ziglang/zig/blob/0.11.0/lib/std/fmt.zig#L22)

- ## [Anonymous struct coercions](https://zig.news/xq/cool-zig-patterns-305o)

- ## [Comptime string intern pool](https://zig.news/xq/cool-zig-patterns-comptime-string-interning-3558)

- ## [Static dispatch (tagged union)](https://zig.news/kristoff/easy-interfaces-with-zig-0100-2hc5)

- ## [Dynamic dispatch (fat pointer)](https://github.com/ziglang/zig/blob/0.11.0/lib/std/mem/Allocator.zig#L14)

- ## [Static error absence guarantee](https://github.com/ziglang/zig/blob/1d82d7987acf7f020bcc6a976f9887a3556ef79c/lib/std/hash_map.zig#L1563)

- ## [Deferred resource deinitialization](https://github.com/ziglang/zig/blob/0.11.0/lib/std/once.zig#L30)

- ## [Error deferred resource deinitialization](https://github.com/ziglang/zig/blob/0.11.0/lib/std/tz.zig#L92)
