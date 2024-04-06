# convert_heic - Convert HEIC images to any other format supported by ImageMagick

The `convert_heic` function is designed to convert HEIC image files to a specified format using ImageMagick. This function provides flexibility in choosing the output format and offers an option to delete the original HEIC files after conversion.

When my girlfriend bought an iPhone, I needed a way to convert the HEIC files it produced in an easy and effective way and this script was born.

## Features

- **Flexible Output Format:** Allows specifying the output format for the converted images. The supported formats depend on ImageMagick's capabilities.
- **Optional Deletion of Originals:** Provides an option to delete the original HEIC files after successful conversion, helping to free up space.
- **Help Message:** Displays usage information to assist with the correct usage of the function.

## Installation

Use the Zrep Package Installer (zpi) to install:

```
zpi install kekePower/convert_heic
zpi enable kekePower/convert_heic
```

## Usage

```
convert_heic [-d] [-h] [--format=<format>] [format]
Options
-d                 : Delete original HEIC files after conversion.
-h                 : Show the help message with usage information.
--format=<format>  : Specify the output format for the conversion (default: png).
format             : Specify the output format without using the --format option
convert_heic -d --format=png        # Convert to PNG and delete originals.
convert_heic --format=jpg           # Convert to JPG and keep originals.
convert_heic gif -d                 # Convert to GIF and delete originals.
convert_heic -d png                 # Convert to PNG and delete originals.
convert_heic                        # Convert to PNG and keep originals.
```

## Implementation Details

The function parses command-line options to determine the desired output format and whether the original files should be deleted. It iterates over all files in the current directory, identifies HEIC files (case-insensitive), and uses ImageMagick's `convert` command to perform the conversion. If the `-d` option is specified, the original HEIC files are deleted after conversion.

## Requirements

- ImageMagick must be installed and accessible in the system's PATH for the conversion to work.