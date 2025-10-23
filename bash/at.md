# execute command at exact time
interactively:

```shell
at 11:00
# then inside at's prompt:
# touch touched_at_11_00
# press Ctrl+D to finish
```

one-liner: 

```shell
echo 'touch touched_at_11_00' | at 11:00
```
