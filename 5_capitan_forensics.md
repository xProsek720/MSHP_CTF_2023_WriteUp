# 5 - capitan forensics

## [Come Back to README](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/README.md)

## Solve

Now we turn on the WireShark

I know that we are searching for two packets so...

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/5/1.png)

Let's look at IPv4 statistics

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/5/2.png)

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/5/3.png)

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/5/4.png)

Now I will querry for that Ip address with count of two

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/5/5.png)

Key of cipher is: ```0x42```

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/5/6.png)

And here is the flag xor'ed with HEX key of ```0x42```

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/5/7.png)

then i've reported the flag to the bot:

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/5/8.png)

## By The Way

Thanks to [@tturba](https://github.com/tturba/) for tips for WireShark on training

## [Come Back to README](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/README.md)