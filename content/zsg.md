+++
title = "Zig Style Guide"
date = 2023-10-27

[taxonomies]
categories = ["table"]
tags = ["ziglang", "software"]
+++

Very opinionated extension to the [Zig style guide](https://ziglang.org/documentation/master/#Style-Guide).

<!-- more -->

# **Top-to-bottom source file hierarchy**

| File Group |     Sorting Order      | Letter Case |
|:----------:|:----------------------:|:-----------:|
| Directory  | Descending by alphabet | kebab-case  |
| Namespace  | Descending by alphabet | snake_case  |
|   Struct   | Descending by alphabet |  TitleCase  |

# **Top-to-bottom file container layout**

> For imports, aliases, and namespaces first list std, then modules, then files.

|    Item Group    |    Sorting Order     |     Letter Case      |
|:----------------:|:--------------------:|:--------------------:|
|     Imports      | Ascending by length  |    Original case     |
|    Namespaces    | Ascending by length  |    Original case     |
|     Aliases      | Descending by length |    Original case     |
| Global variables | Ascending by length  | SCREAMING_SNAKE_CASE |
| Global constants | Ascending by length  | SCREAMING_SNAKE_CASE |
|    Error sets    | Descending by length |      TitleCase       |
|      Enums       | Descending by length |      TitleCase       |
|      Unions      | Descending by length |      TitleCase       |
|     Structs      | Descending by length |      TitleCase       |
|      Fields      | Descending by length |      snake_case      |
|    Functions     | Descending by length |      camelCase       |
|      Tests       | Descending by length |      camelCase       |
