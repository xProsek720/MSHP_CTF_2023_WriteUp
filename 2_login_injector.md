# 2 - Login Injector

## [Come Back to README](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/README.md)

## Solve

First thing I've tried was ``` `OR 1=1 -- ``` and it didn't work :(

Not easiest SQL Injection:

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/2/1.png)

but I thought about a tip from the challange that Adam doens't like even numbers 

As far as I remember it was in the source of the website

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/2/2.png)

so i tried with even numbers like:

```
` OR 2=2 --
```

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/2/3.png)

And got the flag that should be reversed:

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/2/4.png)

How to easily reverse text in python [ you can do it even shorter :) ]

```
textToReverse = "XXXX_XXXXXXXXX"
print(textToReverse[::-1])
```

After reversing the flag just had to report it to the bot:

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/2/5.png)

## [Come Back to README](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/README.md)