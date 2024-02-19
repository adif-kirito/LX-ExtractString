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
# Awk Command

## Example

```bash
user@ubuntu:~$ cat employee.txt
ali manager account 45000
abu clerk account 25000
malik manager sales 50000
kamarul manager account 47000
```

### 1. Match (/_text_/)

```bash
user@ubuntu:~$ awk '/manager/ {print}' employee.txt
ali manager account 45000
malik manager sales 50000
kamarul manager account 47000
```

### 2. Split into fields

```bash
user@ubuntu:~$ awk '{print $1,$4}' employee.txt 
ali 45000
abu 25000
malik 50000
kamarul 47000
```

### 3. Use of NR built-in variables (Display Line Number)  

```bash
user@ubuntu:~$ awk '{print NR,$0}' employee.txt 
1 ali manager account 45000
2 abu clerk account 25000
3 malik manager sales 50000
4 kamarul manager account 47000
```

### 4. Use of NF built-in variables (Display Last Field)  

```bash
user@ubuntu:~$ awk '{print $1,$NF}' employee.txt 
ali 45000
abu 25000
malik 50000
kamarul 47000
```

### 5. Display Line From 2 to 4 using NR

```bash
user@ubuntu:~$ awk 'NR==2, NR==4 {print NR,$0}' employee.txt 
ali 45000
abu 25000
malik 50000
kamarul 47000
```

### 6. To print the first item along with the row number(NR) separated with " – " from each line

```bash
user@ubuntu:~$ awk '{print NR "- " $1 }' employee.txt 
1- ali
2- abu
3- malik
4- kamarul
```

### 7. To return the second column/item

```bash
user@ubuntu:~$ awk '{print $2}' employee.txt 
manager
clerk
manager
manager
```

### 8. To count the lines in a file

```bash
user@ubuntu:~$ awk 'END { print NR }' employee.txt 
4
```

### 9. Printing lines with more than 10 characters

```bash
user@ubuntu:~$ awk 'length($0) > 25' employee.txt 
kamarul manager account 47000
```

### 10. To find/check for any string in any specific column

```bash
user@ubuntu:~$ awk '{ if($4 == "25000") print $0;}' employee.txt 
abu clerk account 25000
```

<!-- ----------------------------------------------------- -->
# expr Command

expr substr _<input_string>_ _<start_index>_ _<length>_

```bash
user@ubuntu:~$ expr substr "0123Linux9" 5 5
Linux
```
