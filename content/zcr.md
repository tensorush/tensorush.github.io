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
const val: MyItem.MyTag = .Value; // Nope
const val = MyItem.MyTag.Value;   // Yep
```

- ## Make everything constant by default

```zig
var item = MyItem{};   // Nope
const item = MyItem{}; // Yep
```

- ## Use type names instead of type casts

```zig
const fld = @as(u8, @intCast(item.fld)); // Nope
const fld: u8 = @intCast(item.fld);      // Yep
```

- ## Don't use any extra labels for naming pointers

```zig
for (items) |*item_ptr| {...} // Nope
for (items) |*item| {...}     // Yep
```

- ## Use a short, consistent suffix for naming optionals

```zig
if (maybe_item) |item| {...} // Nope
if (item_opt) |item| {...}   // Yep
```

- ## Prefer anonymous structs whenever the type is inferred

```zig
return MyItem{ .fld = 42 }; // Nope
return .{ .fld = 42 };      // Yep
```

- ## Specify the tested entity's name as the test function's name

```zig
test "MyItem" {...} // Nope
test MyItem {...}   // Yep
```

- ## Use Self only for file structs as well as nameless and anonymous structs

```zig
// Nope
const Item = struct {
    const Self = @This();

    self_opt: ?*Self = null,
};

// Yep
pub fn Item(comptime T: type) type {
    return struct {
        const Self = @This();

        self_opt: ?*Self = null,
        fld: T,
    };
}
```
