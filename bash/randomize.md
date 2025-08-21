# generate random number in range A <= n <= B

```shell
shuf -i 0-100 -n 1
shuf -i 100-200 -n 1
shuf -i 1000000-99999999999 -n 1
```

# generate 32 characters random string of lowercase letters and numbers

```shell
LC_CTYPE=C tr -dc 'a-z0-9' </dev/urandom | head -c 32; echo
```