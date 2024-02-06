+++
title = "Nu Table Format"
description = ""
date = "2023-11-19T18:01:37.655Z"
draft = true
tags = ["NuShell" ]
+++
Proposing enhancements to Nushell `table` command.

The general problem is it's hard to create a table where each column can be styled and aligned.

<!--more-->
Nu has features that are close, but not quite:
* Table "theme"
Controls things like border style and compressed vs expanded, but doesn't manage styling of column contents
* Nu Value "theme" and styling
Specifies coloring of Nu value, and can be value-dependent.  But it applies (the same way) in all to-string rendering contexts and doesn't handle alignment (nor should it, that's table column specific).

So we need something new, here bravely named "table formatting":
* Allows, e.g, an int value to be formatted differently based on the column it appears in.
* Allows specifying alignment of rendered value in column: left, center and right adjusted.
* Special attention to formating of real numbers: decimal align, sci vs engineering notation.  
* Special attention to padding for strings (fill with specified character) (a lot like existing `fill`)


# Problems
# Ideas to kick around
## capabilities already in `crate\nu-table`
Seems to be lots of flexibility there, but mostly not exposed in `table`.
## how to specify the table format
### Explicit per-column format
e.g the `table` command has a "format" argument which is a record `<column>: {|value, phase| }`, where `phase` might be "set-width" (to estimate a good width for this column, based on values) or "render" (render the value for display)
There *has* to be a way to do this, though it might be some static configuration (like value themes) or an argument on `table`.
### type names for tables and records (like struct decls)
This is two step:
* Specify per-column styling, as above
* Provide a way to declare a struct name for a record or table, where the name maps to a per-column styling , as defined above
    * this is a step towards named structs in Nu, format might be: `<name>{}` or `{<name> <col1>: <value> ... }`.  Many other attributes could be defined for a named struct: methods, constructors, etc.
# Proposal