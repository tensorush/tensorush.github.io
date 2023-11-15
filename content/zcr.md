+++
title = "Zig Code Review"
date = 2023-11-12

[taxonomies]
forms = ["code"]
themes = ["ziglang", "software"]
+++

Minimal snippet reviews of Zig code.

<!-- more -->

- ## Use type names instead of type casts

```zig
const x: u8 = @intCast(rect.x);      // Yep
const x = @as(u8, @intCast(rect.x)); // Nope
```

- ## Prefer anonymous structs whenever the type is inferred

```zig
return .{ .x = 42 };        // Yep
return MyStruct{ .x = 42 }; // Nope
```

- ## Use a short consistent suffix when naming optional types

```zig
if (item_opt) |item| {...}   // Yep
if (maybe_item) |item| {...} // Nope
```

- ## Specify the tested entity's name as its test function name

```zig
test MyStruct {...}   // Yep
test "MyStruct" {...} // Nope
```
