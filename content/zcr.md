+++
title = "Zig Code Review"
date = 2023-11-12
draft = true

[taxonomies]
categories = ["code"]
tags = ["ziglang", "software"]
+++

Minimal snippet reviews of Zig code.

<!-- more -->

- ## Specify type names instead of type casts

```zig
const x: u8 = @intCast(rect.x);      // Do
const x = @as(u8, @intCast(rect.x)); // Don't
```

- ## Prefer anonymous structs whenever the type is inferred

```zig
return .{ .x = 42 };        // Do
return MyStruct{ .x = 42 }; // Don't
```
