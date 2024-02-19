# Cut Command

## Flags

|     Option    |                                     Description                                     |
|:-------------:|:-----------------------------------------------------------------------------------:|
|      `-b`     |               Selects only the bytes specified in LIST (ex; -b 1-3,7)               |
|      `-c`     |             Selects only the characters specified in LIST (ex; -c 1-3,7)            |
|      `-d`     |       Uses DELIM as the field delimiter character instead of the tab character      |
|      `-f`     |   Selects only the fileds specified in LIST, seperated by the delimiter character   |
|      `n`      |     Do not split multi-byte characters (no effect unless -b or -c is specified)     |
| `-complement` | Invert the selection of fields/characters. Print the fields/characters not selected |
<br>

## Example

```bash
user@ubuntu:~$ cat state.txt
Selangor
Johor
Melaka
Kuala Lumpur
Sabah
```

### 1. Bytes (-b)

List with ranges:
```bash
user@ubuntu:~$ cut -b 1-3 state.txt
Sel
Joh
Mel
Kua
Sab
```

List without ranges:
```bash
user@ubuntu:~$ cut -b 1,2,3 state.txt
Sel
Joh
Mel
Kua
Sab
```

Show from selected bytes to end byte of a line:
```bash
user@ubuntu:~$ cut -b 3- state.txt
langor
hor
laka
ala Lumpur
bah
```

<!-- ----------------------------------------------------- -->
### 2. Column (-c)

Extract specific characters:
```bash
user@ubuntu:~$ cut -c 1,3,5 state.txt
Sln
Jhr
Mlk
Kaa
Sbh
```

Extract first 3 characters:
```bash
user@ubuntu:~$ cut -c 1-3 state.txt
Sel
Joh
Mel
Kua
Sab
```

Show from selected character to end character of a line:
```bash
user@ubuntu:~$ cut -c 3- state.txt
langor
hor
laka
ala Lumpur
bah
```

<!-- ----------------------------------------------------- -->
# awk Command
### 3. Field (-f)

Extract specific characters:
```bash
user@ubuntu:~$ cut -d " " -f 1 state.txt
Selangor
Johor
Melaka
Kuala
Sabah
```

<!-- ----------------------------------------------------- -->
# expr Command
