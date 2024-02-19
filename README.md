# LX-ExtractString

<!-- ----------------------------------------------------- -->
## Cut Command

### Flags

|     Option    |                                     Description                                     |
|:-------------:|:-----------------------------------------------------------------------------------:|
|      `-b`     |               Selects only the bytes specified in LIST (ex; -b 1-3,7)               |
|      `-c`     |             Selects only the characters specified in LIST (ex; -c 1-3,7)            |
|      `-d`     |       Uses DELIM as the field delimiter character instead of the tab character      |
|      `-f`     |   Selects only the fileds specified in LIST, seperated by the delimiter character   |
|      `n`      |     Do not split multi-byte characters (no effect unless -b or -c is specified)     |
| `-complement` | Invert the selection of fields/characters. Print the fields/characters not selected |
<br>

### Example

```bash
user@ubuntu:~$ cat state.txt
Selangor
Johor
Melaka
Negeri Sembilan
Kuala Lumpur
Perak
Sabah
Serawak
```


### 1. Bytes (-b)

List 
```bash
user@ubuntu:~$ cut -b 1-3 <<< '123Selangor789'
123
```

### 2. Install Docker compose

```
sudo apt-get install docker-compose
```

![Alt text](https://github.com/adif-kirito/Docker-Assignment/blob/main/img/Capture.PNG)

## 3. Clone repo

```
git clone https://github.com/adif-kirito/Docker-Assignment.git
```

## 4. Build docker compose

```
docker-compose build
```

## 5. Up docker compose

```
docker-compose up
```

## 6. Verify

Go to browser, enter http://*Host IP*/

![Alt text](https://github.com/adif-kirito/Docker-Assignment/blob/main/img/Capture.PNG)
