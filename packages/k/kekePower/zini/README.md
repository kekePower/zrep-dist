# zini
A Zsh INI file reader.

I created this Zsh function as part of my [Quick Site Generator 2](https://github.com/kekePower/qsgen2) script to read the config file.

### Example INI file

```
; This is a comment
[section]
name = value

[other_section]
name = value
```

### Usage

Place the file ```zini``` in your ```fpath``` and use Zsh's ```autoload``` to load the function.

```
#!/usr/bin/zsh

# You can also add your own paths to fpath
# and place zini there.
fpath=(${HOME}/zsh-functions $fpath)
autoload zini
zini /path/to/your/ini-file
```

Then you can fetch the values like this

```
${config[section_name]}
${config[other_section_name]}
```

