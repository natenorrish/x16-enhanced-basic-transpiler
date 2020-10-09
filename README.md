# Enhanced BASIC Transpiler
 Convert an enhanced version of BASIC to standard BASIC.
 
 Line numbers are not required, nor are they recommended with this transpiler, as they will be automatically inserted for you.

## Usage
NOTE: NodeJS is required

From a command prompt:
```
node convert input.bas output.bas
node convert -x -r input.bas output.bas
convert input.bas output.bas
```

```
X16 Enhanced Basic Transpiler

Usage: convert [-OPTIONS] src.bas dst.bas
   or: node convert src.bas dst.bas

OPTIONS:
--------

-x    Run X16 Emulator
-r    Run program (auto add CLS and RUN to the end)
-p    Use PETSCII character set

```
 
## Syntax

### Variables
Currenly all variables must have a type character ($, %, #). This will be fixed in a future version to allow no type character.

```
SOME_STRING$ = "testing"           ' AA$ = "testing"
INT_VAR% = 10                      ' AB% = 10
NUM_VAR# = 20                      ' AC = 20
```


### Labels

```
X% = 10
IF X% = 10 THEN GOSUB @SUB_ROUTINE_LABEL

END

@SUB_ROUTINE_LABEL:
    PRINT "Inside a subroutine", X%
    RETURN
```

### Define

C/C++ style define directive - all references to the defined variable will be replaced with the actual value:

```
#DEFINE SOME_DEF_VAR    10
```

