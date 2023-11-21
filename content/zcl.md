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

- ## Root library file should have the same name, reference tests, expose the public API and error set.

```zig
//! Root library file `library_name.zig` that exposes the public API.

const std = @import("std");

pub const api = @import("api.zig");

pub const Error = error{
    Value,
};

test {
    std.testing.refAllDecls(@This());
}
```
