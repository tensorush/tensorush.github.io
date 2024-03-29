+++
title = "Zig Code Style"
date = 2023-10-27

[taxonomies]
types = ["table"]
tags = ["zig"]
+++

Very opinionated extension to the [Zig style guide](https://ziglang.org/documentation/master/#Style-Guide).

<!-- more -->

# **Top-to-bottom source file hierarchy**

|   File Group   |       Sorting Order       | Letter Case |
|:--------------:|:-------------------------:|:-----------:|
|   Directory    | Descending alphabetically | kebab-case  |
| Namespace file | Descending alphabetically | snake_case  |
|  Struct file   | Descending alphabetically |  TitleCase  |

# **Top-to-bottom file container layout**

For imports, aliases, and namespaces first list std, then modules, then files.

|     Item Group      |    Sorting Order     |     Letter Case      |
|:-------------------:|:--------------------:|:--------------------:|
|       Imports       | Ascending by length  |    Original case     |
|     Namespaces      | Ascending by length  |    Original case     |
|  Global variables   | Ascending by length  | SCREAMING_SNAKE_CASE |
|  Global constants   | Ascending by length  | SCREAMING_SNAKE_CASE |
|    Type aliases     | Ascending by length  |      TitleCase       |
|     Error sets      | Descending by length |      TitleCase       |
|        Enums        | Descending by length |      TitleCase       |
|       Unions        | Descending by length |      TitleCase       |
|       Structs       | Descending by length |      TitleCase       |
|  Error set values   | Ascending by length  |      TitleCase       |
|     Enum values     | Descending by length |      TitleCase       |
|  Union enum fields  | Descending by length |      TitleCase       |
|    Union fields     | Descending by length |      snake_case      |
|    Struct fields    | Descending by length |      snake_case      |
| Init/deinit methods | Ascending by length  |      camelCase       |
|    Other methods    | Descending by length |      camelCase       |
|  Utility functions  | Descending by length |      camelCase       |
|  Test declarations  |    Original order    |      snake_case      |
