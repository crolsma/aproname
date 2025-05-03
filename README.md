# aproname

## Summary

Detects invalid and problematic pathname patterns,
accounting for both unix-like and Microsoft OSes.

Patterns include:

1. POSIX Portable Filename Character Set
1. ustar pathname length restrictions
1. MS-DOS and Microsoft Windows restrictions
1. Additional restrictions to avoid common usability problems

## Usage

Check pathnames given as arguments:

`aproname pathname...`

Check the pathnames in a directory tree:

`find path... -exec aproname {} +`

Check pathnames from STDIN:

`... | xargs -0 aproname`

Invalid pathnames are printed to STDOUT with a summary of problems for each name,
and the script returns exit code 1 if any problematic patterns are found.
Otherwise it returns exit code 0.

## References

- [Portable Filename Definition](https://pubs.opengroup.org/onlinepubs/9699919799.2018edition/basedefs/V1_chap03.html#tag_03_281)
- [Portable Filename Character Set](https://pubs.opengroup.org/onlinepubs/9699919799.2018edition/basedefs/V1_chap03.html#tag_03_282)
- [Pathname Definition](https://pubs.opengroup.org/onlinepubs/9699919799.2018edition/basedefs/V1_chap03.html#tag_03_271)
- [Pathname Resolution](https://pubs.opengroup.org/onlinepubs/9699919799.2018edition/basedefs/V1_chap04.html#tag_04_13)
- [ustar format](https://pubs.opengroup.org/onlinepubs/9699919799.2018edition/utilities/pax.html#tag_20_92_13_06)
- [ustar portability](https://mgorny.pl/articles/portability-of-tar-features.html)
- [Microsoft Windows filenames](https://docs.microsoft.com/en-us/windows/win32/fileio/naming-a-file)
- [Microsoft OneDrive filenames](https://support.microsoft.com/en-us/office/restrictions-and-limitations-in-onedrive-and-sharepoint-64883a5d-228e-48f5-b3d2-eb39e07630fa)
- [Commentary on safe filenames](https://dwheeler.com/essays/fixing-unix-linux-filenames.html)
