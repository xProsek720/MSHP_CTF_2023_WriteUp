# 4 - $reverseme, harry

## [Come Back to README](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/README.md)

## Solve

Like the description says there is flag hidden inside of binary

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/4/1.png)

I used strings and gdb (GOD BLESS WSL), but forgot to make a screen, sorry 

```
strings new
```

Part of strings:

```
(...)
GLIBC_2.2.5
PTE1
u+UH
ICo7JDoJTzkKO0AdMFAQM1c9JRIKBA==                  <==== FLAG!
GQpXJFNRFBRSJQMuQQ==
Wprowadz klucz:
mystery_key                                       <==== XOR key
Uzyskales dostep do ukrytej funkcjonalnosci!
Flaga: %s
Klucz jest niepoprawny!
:*3$"
GCC: (Ubuntu 11.3.0-1ubuntu1~22.04) 11.3.0
Scrt1.o
__abi_tag
crtstuff.c
deregister_tm_clones
__do_global_dtors_aux
completed.0
__do_global_dtors_aux_fini_array_entry
frame_dummy
__frame_dummy_init_array_entry
new.c
__FRAME_END__
__GNU_EH_FRAME_HDR
_GLOBAL_OFFSET_TABLE_
_DYNAMIC
(...)
```

inside WSL:

```
gdb new
```

inside gdb shell:

```
gdb>disassemble main
```

part of asm main function code

```
(...)
  0x000000000000148a <+24>:    mov    %rax,-0x8(%rbp)
   0x000000000000148e <+28>:    xor    %eax,%eax
   0x0000000000001490 <+30>:    lea    0xb71(%rip),%rax        # 0x2008
   0x0000000000001497 <+37>:    mov    %rax,%rdi
   0x000000000000149a <+40>:    callq  0x13b2 <base64_decode>
   0x000000000000149f <+45>:    mov    %rax,-0x90(%rbp)
   0x00000000000014a6 <+52>:    lea    0xb7c(%rip),%rax        # 0x2029
   0x00000000000014ad <+59>:    mov    %rax,%rdi
   0x00000000000014b0 <+62>:    callq  0x13b2 <base64_decode>
   0x00000000000014b5 <+67>:    mov    %rax,-0x88(%rbp)
   0x00000000000014bc <+74>:    lea    0xb7b(%rip),%rax        # 0x203e
   0x00000000000014c3 <+81>:    mov    %rax,%rdi
   0x00000000000014c6 <+84>:    mov    $0x0,%eax
   0x00000000000014cb <+89>:    callq  0x1130 <printf@plt>
(...)
```

going further we can see:

```
(...)
   0x00000000000014fc <+138>:   callq  0x1309 <xor_encrypt>
   0x0000000000001501 <+143>:   mov    %rax,-0x80(%rbp)
   0x0000000000001505 <+147>:   mov    -0x88(%rbp),%rdx
   0x000000000000150c <+154>:   mov    -0x80(%rbp),%rax
   0x0000000000001510 <+158>:   mov    %rdx,%rsi
   0x0000000000001513 <+161>:   mov    %rax,%rdi
   0x0000000000001516 <+164>:   callq  0x1200 <strcmp@plt>
   0x000000000000151b <+169>:   test   %eax,%eax
   0x000000000000151d <+171>:   jne    0x1574 <main+258>
   0x000000000000151f <+173>:   lea    0xb3a(%rip),%rax        # 0x2060
   0x0000000000001526 <+180>:   mov    %rax,%rdi
   0x0000000000001529 <+183>:   callq  0x1160 <puts@plt>
   0x000000000000152e <+188>:   mov    -0x90(%rbp),%rax
   0x0000000000001535 <+195>:   lea    0xb16(%rip),%rdx        # 0x2052
   0x000000000000153c <+202>:   mov    %rdx,%rsi
   0x000000000000153f <+205>:   mov    %rax,%rdi
   0x0000000000001542 <+208>:   callq  0x1309 <xor_encrypt>
   0x0000000000001547 <+213>:   mov    %rax,-0x78(%rbp)
   0x000000000000154b <+217>:   mov    -0x78(%rbp),%rax
   0x000000000000154f <+221>:   mov    %rax,%rsi
   0x0000000000001552 <+224>:   lea    0xb34(%rip),%rax        # 0x208d
   0x0000000000001559 <+231>:   mov    %rax,%rdi
   0x000000000000155c <+234>:   mov    $0x0,%eax
   0x0000000000001561 <+239>:   callq  0x1130 <printf@plt>
(...)
```

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/4/2.png)

I had to base64 decode string and then just xor encrypt it with key: mystery_key

then i've reported the flag to the bot:

![ctf](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/media/4/3.png)

## By The Way

damn I need to learn asm, becouse I want to understand it more! :D

## [Come Back to README](https://github.com/xProsek720/MSHP_CTF_2023_WriteUp/blob/main/README.md)
