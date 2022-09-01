# µfmt-autoflake

[µfmt-autoflake][] is a code formatter and import sorter for Python and Visual Studio Code,
built on top of [black][] and [µsort][] and [autoflake][]:

> Black makes code review faster by producing the smallest diffs possible.
  Blackened code looks the same regardless of the project you’re reading.
> μsort is a safe, minimal import sorter. Its primary goal is to make no “dangerous”
  changes to code, and to make no changes on code style.
> µfmt formats files in-memory, first with µsort and then with black, before
writing any changes back to disk. This enables a combined, atomic formatting steps in
VS Code, without any chance of conflict or intermediate changes between the import
sorter and the code formatter.
> autoflake removes unused imports.

Note:

- This extension requires Python version 3.7 or newer.
- The extension comes bundled with µfmt `2.0`.
  Older versions of µfmt may work, but are not supported.

## Usage

Once installed, "µfmt-autoflake" will be available as a formatter for Python files
(extension id: `omnilib.ufmt`).
µfmt-autoflake can be set as the default formatter by adding the following to your settings:

```json
"[python]": {
    "editor.defaultFormatter": "mikoz.ufmt-autoflake"
}
```

or through the command pallete option "Format Document With...":

Be sure to disable the legacy Python formatter, if enabled:

```json
"python.formatting.provider": "none"
```

## Format on Save

VS Code can automatically format your Python files when saving by adding the following
to your settings:

```json
"[python]": {
    "editor.defaultFormatter": "mikoz.ufmt-autoflake",
    "editor.formatOnSave": true
}
```

## Resources

- [µfmt documentation][µfmt]
- [black documentation][black]
- [µsort documentation][µsort]
- [autoflake documentation][autoflake]

[black]: https://black.rtfd.io
[µsort]: https://usort.rtfd.io
[µfmt]: https://ufmt.omnilib.dev
[autoflake]: https://github.com/PyCQA/autoflake
[µfmt-autoflake]: https://github.com/34j/vscode-ufmt-autoflake