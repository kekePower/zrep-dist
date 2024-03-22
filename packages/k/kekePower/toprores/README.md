# Toprores Zsh Function

Convert your video files to the ProRes format effortlessly with the `toprores` Zsh function. Utilizing `ffmpeg`, this function enables the conversion of video files in the current directory to the Apple ProRes format, ensuring high-quality video output suitable for professional editing workflows. `toprores` offers simplicity whether converting a single file, multiple files of a specific extension, or all video files in the directory.

## Why?

I started to edit videos using DaVinci Resolve and it doesn't support the widely used video format `mp4`. After a bit of research, I found that the `prores` video format was the best option for it. I then created a short script for it that has done the job for me for a long time, however, it was now time to expand on this script and make it better.

This new version is a lot better and more flexible than the original and works really great for my personal use.

## Features

- **Convert Single File**: Specifically convert a given video file to ProRes format.
- **Batch Convert by Extension**: Convert all video files of a given extension in the current directory.
- **Auto-Convert All Videos**: Without any parameters, find and convert all video files in the current directory.
- **Custom Output Directory**: Define a custom directory for converted files, set once and remembered for future conversions.

## Prerequisites

- `ffmpeg`: Essential for video file conversion. Install from [ffmpeg.org](https://ffmpeg.org/download.html) or through your OS's package manager.
- `zrep`: Download it from [the git repository](https://git.kekepower.com/kekePower/zrep)

## Installation

1. **`zrep install kekePower/toprores`**
2. **`zrep enable kekePower/toprores`**
3. **`source ~/.zrep_addons`**

If it doesn't work right away, try `zsh -l` to launch Zsh as a log-in shell.

## Usage

```
toprores [file|extension]
```

- **No Parameters**: Converts all video files (.mp4, .mkv, .avi, .mov) in the current directory.
- **Specific File**: Converts a named file to ProRes format.
- **By Extension**: Converts all files with a specified extension.

### Output Directory

Upon first run, `toprores` will ask for an output directory name, saved in `~/.toprores` for future use. To change, edit or delete `~/.toprores`.

## License

`toprores` is open-source, available for both personal and commercial use.
