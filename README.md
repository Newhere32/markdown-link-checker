# Markdown Link Checker

A lightweight offline checker for relative links and image paths in Markdown files. It helps catch broken local links before publishing a repository.

## Features

- Scans Markdown files recursively beneath a chosen directory.
- Checks inline relative links and Markdown image paths.
- Ignores web URLs, protocol-relative URLs, email links, and anchor-only links.
- Reports the Markdown file, line number, and unresolved target.
- Fails with exit code `1` if broken or out-of-root local links are found.
- Uses only the Python standard library.

## Requirements

Python 3.10 or newer.

## Quick start

```bash
python -m markdown_link_checker .
python -m markdown_link_checker ./docs
```

The checker validates that linked local files or directories exist. It does not verify that a `#fragment` anchor exists inside the destination document, and it does not check whether external web links are reachable.

## Supported syntax

This checker handles ordinary inline Markdown links such as `[guide](docs/guide.md)` and images such as `![diagram](images/diagram.png)`. It is intentionally not a full Markdown parser; reference-style links and unusual nested-parenthesis URLs may not be recognized.

## Development and tests

```bash
python -m unittest discover -s tests -v
```

## Licence

Released under the [MIT License](LICENSE).
