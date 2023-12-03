+++
title = "Zig Code Review"
date = 2023-11-12

[taxonomies]
types = ["code"]
tags = ["zig"]
+++

Minimal Zig code review snippets.

<!-- more -->

- ## Provide typed literals

```zig
const item: MyItem = .{}; // Nope
const item = MyItem.{};   // Dope
```

- ## Slice when slice is expected

```zig
var buf: [4]u8 = undefined;
const buf_slice = try bufPrint(&buf, "Nope", .{});     // Nope
const buf_slice = try bufPrint(buf[0..], "Dope", .{}); // Dope
```

- ## Make everything constant by default

```zig
var item = MyItem{};   // Nope
const item = MyItem{}; // Dope
```

- ## Use type names instead of type casts

```zig
const fld = @as(u8, @intCast(item.fld)); // Nope
const fld: u8 = @intCast(item.fld);      // Dope
```

- ## Try to avoid type aliasing altogether

```zig
// Nope
const testing = std.testing;

try testing.expect(false);

// Dope
try sdt.testing.expect(true);
```

- ## Provide formatting specifiers for numbers

```zig
std.debug.print("{}", .{int_or_float});  // Nope
std.debug.print("{d}", .{int_or_float}); // Dope
```

- ## Don't use any extra labels for naming pointers

```zig
for (items) |*item_ptr| {...} // Nope
for (items) |*item| {...}     // Dope
```

- ## Initialize tagged union's void fields as enum tags

```zig
const Pet = union(enum) {
    cat: union(enum) {
        siberian: void,
        birman: void,
    },
    dog: Dog,
};

const pet = Pet{ .cat = .{ .siberian = {} } }; // Nope
const pet = Pet{ .cat = .siberian }; // Dope
```

- ## Use a short, consistent suffix for naming optionals

```zig
if (maybe_item) |item| {...} // Nope
if (item_opt) |item| {...}   // Dope
```

- ## Use a short, consistent suffix for naming iterators

```zig
while (iter.next()) |v| {...}          // Nope
while (items_iter.next()) |item| {...} // Dope
```

- ## Prefer anonymous structs whenever the type is inferred

```zig
return MyItem{ .fld = 42 }; // Nope
return .{ .fld = 42 };      // Dope
```

- ## Specify the tested entity's name as the test function's name

```zig
test "MyItem" {...} // Nope
test MyItem {...}   // Dope
```

- ## Use a short, consistent suffix for naming string-formatted values

```zig
const item_name = @tagName(item_tag);    // Nope
const item_tag_str = @tagName(item_tag); // Dope
```

- ## List the expected value before the actual if the type can be inferred

```zig
try sdt.testing.expectEqual(getItem(), exp_item); // Nope
try sdt.testing.expectEqual(exp_item, getItem()); // Dope
```

- ## Defer resource deinitializations right after respective initializations

```zig
// Nope
mutex.lock();

runCriticalSection();

mutex.unlock();

// Dope
mutex.lock();
defer mutex.unlock();

runCriticalSection();
```

- ## Use Self only for file structs as well as nameless and anonymous structs

```zig
// Nope
const Item = struct {
    const Self = @This();

    self_opt: ?*Self = null,
};

// Dope
pub fn Item(comptime T: type) type {
    return struct {
        const Self = @This();

        self_opt: ?*Self = null,
        fld: T,
    };
}
```
