+++
title = "Zig Code Review"
date = 2023-11-12

[taxonomies]
forms = ["code"]
themes = ["ziglang", "software"]
+++

Minimal snippet reviews of Zig code.

<!-- more -->

- ## Provide typed literals

```zig
const val = MyItem.MyTag.Value;   // Yep
const val: MyItem.MyTag = .Value; // Nope
```

- ## Use type names instead of type casts

```zig
const fld: u8 = @intCast(item.fld);      // Yep
const fld = @as(u8, @intCast(item.fld)); // Nope
```

- ## Use a short, consistent suffix for naming optionals

```zig
if (item_opt) |item| {...}   // Yep
if (maybe_item) |item| {...} // Nope
```

- ## Prefer anonymous structs whenever the type is inferred

```zig
return .{ .fld = 42 };      // Yep
return MyItem{ .fld = 42 }; // Nope
```

- ## Specify the tested entity's name as its test function name

```zig
test MyItem {...}   // Yep
test "MyItem" {...} // Nope
```
