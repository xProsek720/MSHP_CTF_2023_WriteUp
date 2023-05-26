# 3 - Stegano Buster

## [Come Back to README](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/README.md)

## Solve

Encrypted message in bits of image

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/3/1.png)

let me see the image

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/3/2.png)

found that in source of website

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/3/3.png)

That was on the new website:

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/3/4.png)

Reversed encryption function (with a lil help of lovely GPT3) [ima lazy], runned .py script

```
    img = Image.open(image_path)
    pixels = img.load()
    binary_msg = ""

    for x in range(img.width):
        for y in range(img.height):
            pixel = list(pixels[x, y])
            for n in range(3):
                lsb = pixel[n] & 1
                binary_msg += str(lsb)
    inverted_msg = ""
    for i in range(0, len(binary_msg), 8):
        byte = binary_msg[i:i + 8]
        char_code = int(byte, 2)
        inverted_msg += chr(char_code)
    print(inverted_msg.encode("utf-8"))
    with open(output_path, 'w') as file:
        file.write(inverted_msg.encode())
```

got the flag

```
    b'MSHP_{vr$LJzTg2#7iWdH}\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x0...
```

and reported flag to the bot:

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/3/5.png)

## [Come Back to README](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/README.md)