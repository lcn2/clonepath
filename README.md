# clonepath

Clone a path under a directory.


# To install

```sh
sudo make install
```


# Example

Clone the tree under `/path/2/clone` into the directory under `/clone/under`:

```sh
$ /usr/local/bin/clonepath /path/2/clone /clone/under
```


# To use

```
/usr/local/bin/clonepath [-h] [-v] [-V] [-n] [[-o] [-m] [-a] | [-d]] [-k] /path/2/clone /clone/under

    -h      print help message and exit
    -v      be verbose (def: be silent except for errors and warnings)
    -V      print version string and exit

    -n      no op, do nothing (def: do, kill, remove as needed)

    -o      change ownership of dirs from /clone/under thru /clone/under/path/2 (def: do not change)
                NOTE: rsync always sets ownership at and below /clone/under/path/2/clone if superuser

    -m      change permission of dirs from /clone/under thru /clone/under/path/2 (def: do not change)
                NOTE: rsync always sets permissions at and below /clone/under/path/2/clone

    -a      clone using absolute canonical path of /path/2/clone (def: clone /path/2/clone as is)
                NOTE: when combined with -o and/or -a and will change dirs at and below /clone/under

    -d      clone directly into /clone/under (def: clone into /clone/under/path/2/clone)
                NOTE: -d conflicts with -o, -m and -a

    -k      keep files and dirs found in target that are not found in source (def: delete them)
                NOTE: without -k, rsync uses the --delete option

    /path/2/clone   clone /path/2/clone under the /clone/under directory
    /clone/under    top directory under which to clone /path/2/clone

clonepath version: 1.0.0 2025-04-07
```


# Reporting Security Issues

To report a security issue, please visit "[Reporting Security Issues](https://github.com/lcn2/clonepath/security/policy)".
