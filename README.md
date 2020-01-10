# notes

[![](https://github.com/songouyang/notes/workflows/Build%20and%20Deploy/badge.svg)](https://github.com/songouyang/notes/actions?query=workflow%3A%22Build+and+Deploy%22)

本地预览

```console
$ git clone https://github.com/songouyang/notes.git && cd notes
$ git submodule update --init --recursive
$ ln -s `pwd`/source/icarus.yml `pwd`/themes/icarus/_config.yml
$ yarnpkg
$ yarnpkg run server
```
