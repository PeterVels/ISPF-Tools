# ISPF Tools
## Mostly written in Rexx ##

Still a work-in-progress.

Please report all errors.

Happy to accept pull requests to improve the code and fix bugs.

###ALLOCD Instructions###

In SDSF
-Put a **?** next to the job whose output you want to examine
-Use line command SV or SE on JESYSMSG line
-Issue primary command ALLOCD with optional filters:

`ALLOCD {N} {data set filter}`

Both parameters are optional. Parameter order does not matter

Examples
-`ALLOCD`          no filter
-`ALLOCD N`        do not list temp DSNs
-`ALLOCD SYS`      list only DSNs matching 'SYS'
-`ALLOCD N SYS`    list DSNs matching SYS but not temp DSNs
-`ALLOCD PVELS N`  list DSNs matching PVELS but not temp DSNs

Once the data sets and UNIX files are listed, position the cursor
on the item you wish to examine then hit ENTER to browse or F10 to view.
