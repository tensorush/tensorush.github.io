+++
title = "Zig Code Review"
date = 2023-11-12

[taxonomies]
forms = ["code"]
themes = ["zig"]
+++

Minimal snippet reviews of Zig code.

<!-- more -->

- ## Provide typed literals

```zig
const val: MyItem.MyTag = .Value; // Nope
const val = MyItem.MyTag.Value;   // Yup
```

- ## Make everything constant by default

```zig
var item = MyItem{};   // Nope
const item = MyItem{}; // Yup
```

- ## Use type names instead of type casts

```zig
const fld = @as(u8, @intCast(item.fld)); // Nope
const fld: u8 = @intCast(item.fld);      // Yup
```

- ## Don't use any extra labels for naming pointers

```zig
for (items) |*item_ptr| {...} // Nope
for (items) |*item| {...}     // Yup
```

- ## Use a short, consistent suffix for naming optionals

```zig
if (maybe_item) |item| {...} // Nope
if (item_opt) |item| {...}   // Yup
```

- ## Prefer anonymous structs whenever the type is inferred

```zig
return MyItem{ .fld = 42 }; // Nope
return .{ .fld = 42 };      // Yup
```

- ## Specify the tested entity's name as the test function's name

```zig
test "MyItem" {...} // Nope
test MyItem {...}   // Yup
```

- ## Use Self only for file structs as well as nameless and anonymous structs

```zig
// Nope
const Item = struct {
    const Self = @This();

    self_opt: ?*Self = null,
};

// Yup
pub fn Item(comptime T: type) type {
    return struct {
        const Self = @This();

        self_opt: ?*Self = null,
        fld: T,
    };
}
```
