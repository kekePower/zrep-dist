# zini
A Zsh utility for reading and updating INI files.

`zini` is a Zsh function developed as part of the Quick Site Generator 2 (https://github.com/kekePower/qsgen2) script. It provides a convenient way to read configuration files and now also supports updating existing entries or adding new ones directly from the command line.

### Example INI File

    ; This is a comment
    [section]
    name = value

    [other_section]
    name = value

### Setup

To use `zini`, place the `zini` function file in a directory included in your `fpath` and utilize Zsh's `autoload` mechanism to load it.

    #!/usr/bin/zsh

    # Optionally, add your own paths to fpath
    # and place zini in that directory.
    fpath=(${HOME}/zsh-functions $fpath)
    autoload zini

### Usage

`zini` supports two operations: reading an INI file and updating (or adding) a section's key-value pair.

**Reading an INI File**

To read an INI file and load its contents into an associative array named `config`, invoke `zini` with the `read` command followed by the path to the INI file.

    zini read /path/to/your/ini-file

You can then access the configuration values using:

    echo ${config[section_name_key]}
    echo ${config[other_section_name_key]}

**Updating an INI File**

To update an existing entry or add a new one if it doesn't exist, use the `update` command followed by the path to the INI file, the section name, and the key-value pair.

    zini update /path/to/your/ini-file "section" "key=value"

This will either update the value for an existing key within the specified section or add the key-value pair to the section if the key does not exist. If the section itself does not exist, `zini` will create the section and then add the key-value pair.

### Example

Assuming an INI file named `config.ini` with the following content:

    [database]
    user = admin

To update the `user` key to `root`:

    zini update config.ini "database" "user=root"

To add a new key-value pair `password=secret` under the `[database]` section:

    zini update config.ini "database" "password=secret"

To add a new section `[api]` with a key-value pair `key=abc123`:

    zini update config.ini "api" "key=abc123"
