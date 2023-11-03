+++
title = "Zig Style Guide"
date = 2023-10-27

[taxonomies]
categories = ["code"]
tags = ["ziglang", "software"]
+++

Very opinionated extension to the [Zig style guide](https://ziglang.org/documentation/master/#Style-Guide).

<!-- more -->

## 1) Files:

- Source directory: **kebab-case**

- Namespace file: **snake_case**

- Struct file: **TitleCase**

## 2) Top-to-bottom file container layout:

- imports, then aliases, then namespaces (std, then modules, then files)

- globals (variables, then constants): **SCREAMING_SNAKE_CASE**

- error sets: **TitleCase**

- containers (enums, then unions, then structs): **TitleCase**

- fields: **snake_case**

- functions: **camelCase**

- tests: **camelCase**
