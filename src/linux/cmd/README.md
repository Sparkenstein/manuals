# Command Line

### Make a file with x bit size
```
head -c 10000 /dev/zero > ./tmpfile
```
Creates a file of 10kb with exact


### generate random password 

```
date +%s | sha256sum | base64 | head -c 32 ; echo
```
or
```
< /dev/urandom tr -dc _A-Z-a-z-0-9 | head -c${1:-32};echo;
```
or
```
openssl rand -base64 32
```
