how to repro bug

```
onmt_build_vocab -config .\config.yaml
onmt_train -config .\config.yaml
```

produces the error 

"UnicodeDecodeError: 'utf-8' codec can't decode byte 0xe3 in position 0: invalid continuation byte"

changing build_vocab to have this line fixes it:

```with open(save_path, "w",encoding="utf8") as fo:```