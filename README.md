# ISPF Tools written in Rexx #

This repository is a rather eclectic collection of some Rexx routines I've written because I've either needed them, or just for fun.
Please feel free to ask me anything about them, and of course copy them for your own purposes.
If you fix or improve anything here then please collaborate!

I don't ike writing huge programs, so most of these routines are quite small. Some are edit macros, others are a bit more involved, such as
CPUPCT, PVJCL, ALLOCD, PORTSCAN and PL.

This is a work-in-progress.  Please report all errors and omissions. If you need more documentation please let me know.

A huge thanks to Lionel Dyck for being such an inspiration.

### PVJCL Instructions ###

Edit or view some JCL, e.g. **SYS1.SAMPLIB(TESTEXIT)**. Enter `PVJCL` as a primary command

![JCL](images/PVJCL.jcl.png)

![Panel](images/PVJCL.panel.png)

### ALLOCD Instructions ###

Submit a job, for example:

![JCL](images/ALLOCDJ.png)

Wait for it to complete, then in SDSF held output:

- Put a `?` next to the job whose data sets you want to browse or view
- Use line command `SV` or `SE` (*not S*) on the JESYSMSG line

![SV](images/SVcommand.png)

- Issue primary command `ALLOCD` with optional filters:

`ALLOCD {N} {data set filter}`

Both parameters are optional. Parameter order does not matter

Examples

- `ALLOCD`          No filter
- `ALLOCD N`        Do not list temp DSNs
- `ALLOCD SYS`      List only DSNs matching 'SYS'
- `ALLOCD N SYS`    List DSNs matching SYS but not temp DSNs
- `ALLOCD FRED N`   List DSNs matching 'FRED' but not temp DSNs

Once the data sets and UNIX files are listed, position the cursor
on the item you wish to examine then hit ENTER to browse or F10 to view.

![Panel](images/ALLOCDP.png)

### PORTSCAN Instructions ###

Type `TSO PORTSCAN`

Enter values for Hostname or IP address and Ports and either Y or N in `Show error lines?` then hit enter.

![Panel](images/PORTSCAN.panel.png)
