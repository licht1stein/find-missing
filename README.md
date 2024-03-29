# FIND-MISSING
[![PyPI](https://img.shields.io/pypi/v/find-missing)](https://pypi.org/project/find-missing/)
![](https://img.shields.io/badge/maintained-not_intended-red)

Find files missing in a folder. This tool is intended to be used with [pipx](https://pipxproject.github.io/pipx/) as a normal command line tool.

## Installation with PIPX   
```shell script
pip install pipx
pipx install find-missing
```

## Usage with pipx
```shell script
$ find-missing "foo, bar, spam.jpg"
```

A file `foolitzer.jpg` will be a match without the `--exact` flag.

### Options

#### Exact match only
```shell script
$ find-missing "foo, bar" --exact/-e
```

Looks for exact match, otherwise looks for partial match, so in the above example a file `foo.jpg` will be a match, and a file `foolitzer.jpg` will not.

#### Include directories

```shell script
find-missing "foo, bar" --dirs/-d
```

Will also check against subdirectories of the current directory.

#### Verbose mode
```shell script
$ find-missing "foo, bar" --verbose/-v 

Verbose mode: True. Exact mode: False. Include directories: False
Looking for files: read
Directory content:
        ...
        .gitignore
        README.md
        poetry.lock
        pyproject.toml
        setup.py

Found 0 missing files:
All here!

```

Verbose mode (silent by default)

### List separator
The tool will do it's best to find file names separated by anything. So a comma, a space, a semicolon will all work. The dot, underscore and dash will not as they can all be parts of file names.
