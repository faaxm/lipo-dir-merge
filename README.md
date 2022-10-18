# lipo-dir-merge

This script helps you easily build universal static libraries for macOS.

It takes two directory trees, containing the library, its headers and any other related documents for each architecture (e.g. x86 and ARM) and then merges them to produce a single directory with the universal binary.

While traversing both source directory trees, all files without the `.a` extension are copied from the first tree into the output directory. If a static library is found, it is looked up in the second directory tree and both versions are merged using `lipo`.

Run it like this:
```
$ python3 lipo-dir-merge.py <arm64-dir-tree> <x64-dir-tree> <universal-output-dir>
```

## Resources
* [A blog post on using lipo to build universal binaries](https://www.f-ax.de/dev/2021/01/15/build-fat-macos-library.html)