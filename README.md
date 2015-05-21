# keys(1)

Simple key management tool for `.ssh/authorized_keys`,
intended for use with `git-shell(1)`.

## Usage

* **list**: list keys (with each line numbered)
```
$ keys list
1. ssh-rsa ...
```

* **add**: add keys (one per line)
```
$ ./keys add <~/.ssh/id_rsa.pub 
Added 1 keys
```

* **del**: delete keys (by line numbers)
```
$ keys del 1
Deleted 1 keys
```

## Installation

Copy the `keys` script into the `git-shell-commands` directory of your git
user's home directory, or clone the keys repo to that directory.

```
cp keys ~git/git-shell-commands/
```

If you have the git user's shell set to `git-shell` so that they can only
manage git repos, putting `keys` in the `git-shell-commands` directory lets the
git user manage its ssh authorized keys as well. It could be used
non-interactively as follows:

```
ssh git@example.org keys list
ssh git@example.org keys add ...
ssh git@example.org keys del ...
```

## License

MIT
