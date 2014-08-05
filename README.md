Stout
=====

STylized OUTput for [Lager](https://github.com/basho/lager).

Stout is a better version of the `lager_default_formatter` formatter. It
follows the same pattern, a list of either IO data or tags. In Stout, each tag
can be accompanied by a set of format options.

Example:

```erlang
[
    {date, blackb}, " ",
    {time, yellow}, " ",
    {severity, [color, {format, "~.7s "}]},
    message, "\n"
]
```

Which would yield:

![Example](https://raw.github.com/eproxus/stout/master/screenshot.png)

The main difference is color support (explicit for all tags and automatic for severity) and the possibility to format a tag (using `{format, FmtStr}` that will only be applied if the tag exists. For example, wrapping a tag in `[` and `]` using `{format, "[~s]"}` would only show the brackets if the tag exists.

Options
-------

* `upper` Transform to upper case.
* `lower` Transform to lower case.
* `color` Colorize severity levels (**only** supported for the `severity` tag).
* `{format, Fmt}` Format string according to [`io:format/3`](http://www.erlang.org/doc/man/io.html#format-3).
* `Color` A color supported by the [color](https://github.com/julianduque/erlang-color) library.

