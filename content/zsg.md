+++
title = "Zig Style Guide"
date = 2023-10-27
draft = true

[taxonomies]
categories = ["list"]
tags = ["ziglang", "software"]
+++

Very opinionated style guide for the Zig programming language.

<!-- more -->

- Top-to-bottom container layout:

    - imports then aliases then namespaces (std then packages then locals)

    - globals (vars then consts, pubs then privs)

    - error sets

    - containers (enums then unions then structs)

    - fields

    - functions

    - tests
