---
layout: docs
title: Config Project
---

# Config Project

## syntax of .exvim file

TODO

Check [ex-vimentry](https://github.com/exvim/ex-vimentry) for more details 

## Default Options

### folder_filter_mode (option)

Options:

- include 
- exclude

`folder_filter_mode` tell exVim which filter mode should be used for `folder_filter`. 

### folder_filter (array)

`folder_filter` accept folder names as value. The `folder_filter` will be used to filter 
out the folders in the first level of root directory. It will use the filter rule setted
in `folder_filter_mode`.

Example:

Suppose you have foo,bar,foobar,hello,world in your first level directory.

When you set the filter as: 

```
folder_filter_mode = include
folder_filter += foo,bar
```

Only foo,bar shows in your ex-project browser. 

When you set the filter as: 

```
folder_filter_mode = exclude
folder_filter += foo,bar
```

Only foobar,hello,world shows in your ex-project browser. 

This option affects the following plugins:

- ex-project 
- NERDTree
- ex-config
  - id-utils ( generate id-lang-autogen.map )
  - ctags (TODO)

### file_filter (array)

`file_filter` accept suffix of the file you expect to browse and process in exVim project. 

Example:

```
file_filter += c,cpp
```

The above filter makes exVim accept *.c, *.cpp files. 

This option affects the following plugins:

- ex-project 
- NERDTree
- ex-config
  - id-utils ( generate id-lang-autogen.map )
  - ctags (TODO)

By default, if this option is empty, the id-utils will use `id-lang.map` in `tools/idutils/` for
creating ID. When this option setted, ex-config will create `id-lang-autogen.map` under your `.exvim.project/`
folder, and idutils will use it instead of `id-lang.map`.

### file_ignore_pattern (array)

TODO: Not implement yet.