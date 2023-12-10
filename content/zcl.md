+++
title = "Zig Code Layout"
date = 2023-11-21

[taxonomies]
types = ["code"]
tags = ["zig"]
+++

General advice around structuring Zig codebases.

<!-- more -->

- ## Root directory should contain .git files.

```sh
# .gitattributes
*.zig text eol=lf
*.zon text eol=lf

# .gitignore
zig-cache/
zig-out/
```

- ## Root directory should contain a build.zig.zon file.

```zig
.{
    .name = "<package_name>",
    .version = "<package_version>",
    .dependencies = .{
        .<dependency_package_name> = .{
            .url = "https://<git_hosting/<user>/<repo>/archive/<version_tag_or_commit_hash>.tar.gz",
            .hash = "<dependency_package_hash>",
        },
    },
    .paths = .{""},
}
```

- ## Root executable file should be named `main.zig`.

```zig
//! Executable source file `main.zig` that contains the entrypoint.

pub fn main() void {}
```

- ## Struct source files, which contain fields, should have TitleCase names.

```zig
//! Struct source file `MyFile.zig` that contains fields.

const MyFile = @This();

fld: u8,
```

- ## Namespace source files, which don't contain fields, should have snake_case names.

```zig
//! Namespace source file `my_file.zig` that doesn't contain fields.

// fld: u8,
```

- ## Root library file should have its name, reference tests, expose the public API and error set.

```zig
//! Root library file `{library_name}.zig` that exposes the public API.

const std = @import("std");

pub const api = @import("api.zig");

pub const Error = error{
    Value,
};

test {
    std.testing.refAllDecls(@This());
}
```
