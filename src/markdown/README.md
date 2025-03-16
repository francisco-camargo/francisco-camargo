# Markdown

[Return to top README.md](../../README.md)

## Code Blocks

Formatting code block [guide](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/creating-and-highlighting-code-blocks), [list](https://github.com/github/linguist/blob/master/lib/linguist/languages.yml)of available tags

Some useful tags:

|                    |                  |             |
| :----------------- | :--------------- | :---------- |
| Batchfile          | Jupyter Notebook | R           |
| BibTeX             | Makefile         | bash        |
| Click              | Markdown         | SQL         |
| CSV                | Numpy            | TeX         |
| Dockerfile         | Pickle           | Text        |
| GraphQL            | PowerShell       | TOML        |
| Ignore List        | Python           | Vim Snippet |
| JSON               | Python console   | XML         |
| JSON with Comments | Python traceback | YAML        |

<!--
* bash, recommended
* Batchfile
* BibTeX
* Click
* CSV
* Dockerfile
* GraphQL
* Ignore List
* JSON
* JSON with Comments
* Jupyter Notebook
* Makefile
* Markdown
* Numpy
* Pickle
* PowerShell
* Python
* Python console
* Python traceback
* R
* Shell, not recommended
* SQL
* TeX
* Text
* TOML
* Vim Snippet
* XML
* YAML
-->

## LaTeX equation formatting for Markdown

In a Markdown file, the following syntax

```TeX
$y=mx+b$
```

displays as
$y=mx+b$

## YAML Header

[Guide](https://zsmith27.github.io/rmarkdown_crash-course/lesson-4-yaml-headers.html)

## Pandoc

[Pandoc](https://pandoc.org/) is a document converter. I have been using it to convert from `.md` to `.pdf`. Specifically, I have been using the VSCode extension `vscode-pandoc`.

To run

* Have a markdown file open
* Open the Command Palette (`ctrl + shift + p`)
* Find and run Pandoc
* Select the output format desired

Additionally, here the setting I use:

### Docker

![1742135526567](image/README/1742135526567.png)

### PDF Options

Here I have changed the output font size and margin spacing.q

```bach
-V fontsize=12pt -V geometry:margin=1in
```

![1742135667749](image/README/1742135667749.png)
