# ПоXORим?
## Сложность
Ultra easy

## Описание
На листке с места преступления злоумышленник оставил записку: "Способны ли вы найти меня? cfd8caf7eebce0ffe4bcbfd3e2b8efe4bde2b8bff8fff5edd3ffd3e1b8e0bcebbcf1". На экспертизе выявили, что невидимыми чернилами написано 3 буквы: "XOR". Сможешь ли ты разгадать загадку?

## Решение:
Участникам дан hex флага, все, что от них требуется - это перевести этот hex в байты, а позже перебрать все возможные XOR`ы флага с символами (от 0 до 255)

```python=
from pwn import *


flagBytes = bytes.fromhex("cfd8caf7eebce0ffe4bcbfd3e2b8efe4bde2b8bff8fff5edd3ffd3e1b8e0bcebbcf1")
byte = 0x00
print(flagBytes)
for i in range(256):
    flag = xor(flagBytes, byte).hex()
    a = bytes.fromhex(flag)
    if b"CTF" in a:
        print(a)
    byte = byte + 0x01
```
 
## Флаг
CTF{b0lsh03_n4ch1n43tsya_s_m4l0g0}
