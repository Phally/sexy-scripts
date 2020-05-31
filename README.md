# Sexy scripts to make dev life bearable!

This repository contains scripts for everyday life in macOS / Linux.

I'm sure you can get it to work in Windows Bash or Cygwin as well.

Clone or download this repository and add it to the environment in `~/.zshrc` (for example) using:

```bash
export PATH="${PATH}:/Users/phally/sexy-scripts"
```

## Scripts you want to use

### watchdo – run a command on folder or file change

Watches given folder(s) and runs a given command when something changes.

Extremely useful for Test Driven Development (TDD) or HTTP API development for example.

You don't have to refresh the browser, re-run a command or going back to things like Postman every time you want to execute a request.

It doesn't support aliases as it uses `xargs`. Requires [`fswatch`](https://github.com/emcrisostomo/fswatch/wiki/How-to-Use-fswatch) which can be installed using Homebrew or Apt.

**Usage:**
```bash
watchdo <folder ...> -- <command>
```

**Examples:**
```bash
# Automatically run all PHPunit tests when you save something:
watchdo src -- vendor/bin/phpunit

# Automatically run a single PHPunit test when you save something:
watchdo src -- vendor/bin/phpunit tests/TestCase/Controller/UsersControllerTest.php

# Obviously useful for API development!
# Watch the source code and do a HTTP request on save (with HTTPie):
watchdo src -- http GET http://localhost:3000/project/items.json

# Run a command for the triggered file.
# Here {} is replaced by the full path of the changed file:
watchdo folder1 folder2 -- ls -lah {}
```

## More to come
In time I'll probably add more scripts here.

These scripts are designed to be simple. Although I appreciate contributions a lot, issues or pull requests making them more complex might be closed.

[![License: MIT](https://img.shields.io/badge/License-MIT-brightgreen.svg)](https://opensource.org/licenses/MIT)
