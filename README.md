# µfmt-autoflake

[![GitHub](https://img.shields.io/github/license/34j/vscode-ufmt-autoflake?logo=github&logoColor=%23181717)](https://github.com/34j/vscode-ufmt-autoflake)
[![Visual Studio Marketplace Installs](https://img.shields.io/visual-studio-marketplace/i/mikoz.ufmt-autoflake?logo=visual-studio-code&logoColor=%23007ACC)](https://marketplace.visualstudio.com/items?itemName=mikoz.ufmt-autoflake)
[![Visual Studio Marketplace Version](https://img.shields.io/visual-studio-marketplace/v/mikoz.ufmt-autoflake)](https://marketplace.visualstudio.com/items?itemName=mikoz.ufmt-autoflake)

[µfmt-autoflake][] is a code formatter and import sorter / remover for Python and Visual Studio Code,
built on top of [black][] and [µsort][] and [autoflake][]:

> [Black][] makes code review faster by producing the smallest diffs possible.
  Blackened code looks the same regardless of the project you’re reading.

> [μsort][] is a safe, minimal import sorter. Its primary goal is to make no “dangerous”
  changes to code, and to make no changes on code style.

> [µfmt][] formats files in-memory, first with µsort and then with black, before
writing any changes back to disk. This enables a combined, atomic formatting steps in
VS Code, without any chance of conflict or intermediate changes between the import
sorter and the code formatter.

> [autoflake][] removes unused imports and unused variables as reported by pyflakes.

[![Install Now](https://img.shields.io/badge/-Install%20Now-107C10?style=for-the-badge&logo=visualstudiocode)](https://marketplace.visualstudio.com/items?itemName=mikoz.ufmt-autoflake)

![Example GIF](https://raw.githubusercontent.com/34j/vscode-ufmt-autoflake/main/images/Example1.gif)

Note:

- This extension requires Python version 3.7 or newer.
- The extension comes bundled with µfmt `2.0.0b1`, autoflake `1.5.2`.
  Older versions of µfmt or autoflake may work, but are not supported.
- This extension is a fork of [omnilib/vscode\-ufmt](https://github.com/omnilib/vscode-ufmt)

## Usage

Once installed, "µfmt-autoflake" will be available as a formatter for Python files
(extension id: `mikoz.ufmt-autoflake`).
µfmt-autoflake can be set as the default formatter by adding the following to your settings:

```json
"[python]": {
    "editor.defaultFormatter": "mikoz.ufmt-autoflake"
}
```

or through the command pallete option `Format Document With...`:

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

## For Developers

- Run the following command to init

For details, see [microsoft/vscode\-python\-tools\-extension\-template](https://github.com/microsoft/vscode-python-tools-extension-template)

```shell
git init https://github.com/34j/vscode-ufmt-autoflake
cd ./vscode-ufmt-autoflake
py -3.7 -m venv .venv
"./.venv/scripts/activate"
pip install -U nox
nox --session setup
npm install
```

- To debug, open VSCode and press `F5`
- A messagebox with text `Errors exist after running preLaunchTask 'npm: watch'` will appear. Just `Debug Anyway`. Microsoft is 100% blame to this, it just took me 6 hours to figure out that it could be simply ignored. Just `Debug Anyway`.
- To change the behavior, change codes in server.py and runner.py. Other codes are untouched and does not need to be touched generally.
- To publish package,

```shell
vsce publish
```

- The difference between the original [omnilib/vscode\-ufmt](https://github.com/omnilib/vscode-ufmt) and this project is 
  - `server.py` around line 303
  - `runner.py` around line 64
  - `requirements.in` (add autoflake)
  - `icon.png`
  - `package.json`
  - `LICENSE.txt` `README.md`
