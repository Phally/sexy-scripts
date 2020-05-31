# Scripts for everyday life

This repository contains scripts for everyday life in macOS.

Clone this repository and add it to the environment in `~/.zshrc` using:

```bash
export PATH="${PATH}:/Users/phally/Script"
```

## Available scripts, usages and examples

### watchdo

Requires [`fswatch`](https://github.com/emcrisostomo/fswatch/wiki/How-to-Use-fswatch) which can be installed using Homebrew.

```bash
watchdo <folders> -- <command>
```
---

```bash
# Run a command for the triggered file:
watchdo folder1 folder2 -- ls -lah {}

# Watch source code and do an API call on save:
watchdo config src webroot -- http GET http://192.168.47.50/project/items.json
```
