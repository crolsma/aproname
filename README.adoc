**Summary:**
  Detects problematic pathname patterns, accounting for both Unix-like and Microsoft OSes.  With this, nonportable pathnames can be corrected before problems occur.

**Usage:**
  aproname [files]

  To test all pathnames in a directory tree:
  `find /path/to/directory | aproname`

  Or, if a list of pathnames is written to a file:
  `aproname /path/to/file`
  
  Alternatively, the script can be used interactively by providing no arguments.
  
  Regardless of usage style, the script returns exit code 1 if any problematic patterns are found.

**Requirements:**
  POSIX awk, sh, and utilities
