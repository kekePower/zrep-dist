# tohtml Function Usage Guide

The `tohtml` function is designed to convert source code files into HTML files with syntax highlighting, using either Vim or Neovim as the text editor for processing. This function dynamically determines the content type of the input file and sets the appropriate syntax highlighting before converting it to HTML.

## Prerequisites

- Vim or Neovim installed on your system.
- The `file` command available for determining file MIME types.

## Installation

1. Add the `tohtml` function script to your `.zshrc` file or any script file sourced by it.
2. Restart your terminal session or source the file containing the function to make it available in your current session.

## Usage

```zsh
tohtml [input_file]
```

- `input_file`: The path to the source code file you want to convert to HTML.

The first time you run the function, it will ask whether you want to use Vim or Neovim. Your choice will be saved in the `~/.tohtml` file and used for subsequent conversions.

## Supported File Types

The function attempts to support a wide range of file types by using MIME types to detect the content and set the corresponding Vim filetype for syntax highlighting. Some of the explicitly supported types include:

- C and C++ (code and header files)
- Shell scripts
- Python
- HTML
- JavaScript
- CSS

## Expanding Support

To add support for additional file types, you can modify the function by adding more MIME type mappings to the case statement that assigns the `vim_ft` variable.

## Example

Convert a Python script to HTML with syntax highlighting:

```zsh
tohtml my_script.py
```

This command will process `my_script.py` and create an HTML file named `my_script.py.html` with appropriate syntax highlighting.