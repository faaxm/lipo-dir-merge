# lipo-dir-merge

This script helps you easily build universal static libraries for macOS.

It takes two directory trees, containing the libraries and any other files for each architecture (e.g. x64 and ARM) and then merges them to produce a single directory with the universal binary.

While traversing both directory trees, all files which are static libraries (`.a` files) or mach-O binaries (Typically `.dylib` or executable) are looked up in the second directory tree and both versions are merged using `lipo`. Any other files will be copied into the target directory.

Run it like this:
```
$ python3 lipo-dir-merge.py <arm64-dir-tree> <x64-dir-tree> <universal-output-dir>
```

## Resources
* [A blog post on using lipo to build universal binaries](https://www.f-ax.de/dev/2021/01/15/build-fat-macos-library.html)
* [A blog post on building universal binaries with vcpkg](https://www.f-ax.de/dev/2022/11/09/how-to-use-vcpkg-with-universal-binaries-on-macos/)

## Contribute

Style is enforced by pre-commit:

```
pip install pre-commit
pre-commit install
```
