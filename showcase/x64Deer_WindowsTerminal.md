# WindowsTerminal.exe — decompiler showcase (x64Deer 0.1)

15 of 771 decompiled functions, chosen for size and loops.  
Left: x86-64 disassembly. Right: decompiler output.

Source: <https://github.com/microsoft/terminal/releases/download/v1.25.2733.0/Microsoft.WindowsTerminal_1.25.2733.0_x64.zip>  
SHA-256: `1cbe52914f7437a4f064327383f1b4c45fe2eb8e92d4f8dae0ad7efcb13a20a1 *WindowsTerminal.exe`

<a id="sub_14002b338"></a>

### 1. `sub_14002b338`

C line 9220 · asm line 59016 · 0 loops · 1 branches · 55 asm → 23 C lines

<table>
<tr><th>Assembly</th><th>Decompiled C</th></tr>
<tr><td valign="top">

```nasm

 mov [rsp+0x18], rbp
 mov [rsp+0x20], rsi
 push rdi
 push r14
 push r15
 sub rsp, 0x40
 mov [rsp+0x30], rcx
 mov rdi, rcx
 mov rbp, [rdx]
 xor r15d, r15d
 mov rcx, rbp
 call _strlen
 mov r9d, eax
 mov [rsp+0x28], r15d
 mov r8, rbp
 mov [rsp+0x20], r15
 xor edx, edx
 mov ecx, 0xFDE9
 mov r14, rax
 call _MultiByteToWideChar
 mov esi, eax
 test eax, eax
 jnz 0x000000014002B38B
 mov [rdi], r15
 jmp 0x000000014002B3D0

0x14002b38b:
 mov ecx, esi
 mov [rsp+0x68], rbx
 call sub_140016ae0
 mov [rsp+0x28], esi
 mov r9d, r14d
 mov r8, rbp
 mov ecx, 0xFDE9
 mov rbx, rax
 mov rdx, [rax+0x10]
 mov [rsp+0x20], rdx
 xor edx, edx
 call _MultiByteToWideChar
 lea rcx, [local_1]
 mov [rsp+0x30], r15
 mov [rdi], rbx
 call sub_1400278a0
 mov rbx, [rsp+0x68]

0x14002b3d0:
 mov rbp, [rsp+0x70]
 mov rax, rdi
 mov rsi, [rsp+0x78]
 add rsp, 0x40
 pop r15
 pop r14
 pop rdi
 ret
```

</td><td valign="top">

```c
__int64 sub_14002b338(__int64 param1, __int64 param2)
{
uint64 var_30;
uint64 vv1;
uint64 result0;
uint32 result1;
uint64 result2;
var_30 = param1;
vv1 = *(uint64 *)param2;
result0 = _strlen(vv1);
result1 = _MultiByteToWideChar(0xfde9, 0x0, vv1, result0, 0x0, 0x0);
if (result1 == 0x0)
{
    *(uint64 *)param1 = 0x0;
    return param1;
}
result2 = sub_140016ae0(result1);
_MultiByteToWideChar(0xfde9, 0x0, vv1, result0, *(uint64 *)(result2 + 0x10), result1);
var_30 = 0x0;
*(uint64 *)param1 = result2;
sub_1400278a0(&var_30);
return param1;
}
```

</td></tr>
</table>

<a id="sub_14003c48c"></a>

### 2. `sub_14003c48c`

C line 17872 · asm line 84571 · 0 loops · 1 branches · 51 asm → 19 C lines

<table>
<tr><th>Assembly</th><th>Decompiled C</th></tr>
<tr><td valign="top">

```nasm

 mov [rsp+0x10], rbx
 push rbp
 push rsi
 push rdi
 sub rsp, 0x30
 mov rax, [0x0000000140064200]
 xor rax, rsp
 mov [rsp+0x28], rax
 mov eax, r8d
 mov ebp, r8d
 mov rdi, rcx
 mov dword ptr [local_1], 0x00
 mov rbx, rdx
 lea rsi, [0x0000000140056D70]
 or eax, 0x01
 bsr ecx, eax
 movsxd r8, ecx
 mov rcx, rbx
 mov rsi, [rsi+r8*8]
 add rsi, rbp
 shr rsi, 0x20
 movsxd rdx, esi
 call sub_14003b8cc
 test rax, rax
 jz 0x000000014003C4F8
 mov r8d, esi
 mov edx, ebp
 mov rcx, rax
 call sub_140038988
 mov [rdi], rbx
 jmp 0x000000014003C509

0x14003c4f8:
 mov r9d, esi
 mov r8d, ebp
 mov rdx, rbx
 mov rcx, rdi
 call sub_140039be8

0x14003c509:
 mov rax, rdi
 mov rcx, [rsp+0x28]
 xor rcx, rsp
 call 0x00000001400121C0
 mov rbx, [rsp+0x58]
 add rsp, 0x30
 pop rdi
 pop rsi
 pop rbp
 ret
```

</td><td valign="top">

```c
__int64 sub_14003c48c(__int64 param1, __int64 param2, int param3, int param4)
{
int vv1;
uint64 vv2;
uint64 vv3;
uint64 result0;
vv1 = __bsr((uint32)(param3 | 0x1));
vv2 = vv1;
vv3 = *(uint64 *)(vv2 * 0x8 + (char *)&mem_140056d70);
result0 = sub_14003b8cc(param2, (int)(vv3 + (uint32)param3 >> 0x20), vv2, param4, 0x0);
if (result0 != 0x0)
{
    sub_140038988(result0, param3, vv3 + (uint32)param3 >> 0x20);
    *(uint64 *)param1 = param2;
    return param1;
}
sub_140039be8(param1, param2, param3, vv3 + (uint32)param3 >> 0x20);
return param1;
}
```

</td></tr>
</table>

<a id="sub_140035fd0"></a>

### 3. `sub_140035fd0`

C line 14396 · asm line 75394 · 0 loops · 0 branches · 50 asm → 23 C lines

<table>
<tr><th>Assembly</th><th>Decompiled C</th></tr>
<tr><td valign="top">

```nasm
 arg_1 : qword ; [rsp+0xD0]


 push rbx
 push rsi
 push rdi
 sub rsp, 0xB0
 mov r8d, edx
 mov rsi, rcx
 mov rax, [rcx+0x08]
 mov edx, [rax]
 shr edx, 0x0A
 and edx, 0x03
 mov ecx, r8d
 call sub_14003a860
 mov rbx, rax
 mov [rsp+0xD0], rax
 lea rax, [local_1]
 mov [rsp+0xE0], rax
 lea rdx, [rsi+0x10]
 lea rcx, [local_1]
 call sub_140041b10
 mov rdi, rax
 lea rdx, [rsi+0x30]
 lea rcx, [local_2]
 call sub_140041a28
 mov rdx, rax
 mov r8, rdi
 lea rcx, [local_3]
 call sub_140041bc4
 nop
 mov r8d, ebx
 mov [rsp+0x28], rax
 mov rax, [rsi+0x08]
 mov [rsp+0x20], rax
 mov r9d, [rsp+0xD4]
 mov rdx, [rsi]
 lea rcx, [arg_1]
 call sub_14003eeb4
 nop
 lea rcx, [local_4]
 call sub_140029310
 lea rcx, [local_3]
 call sub_140045f14
 mov al, 0x01
 add rsp, 0xB0
 pop rdi
 pop rsi
 pop rbx
 ret
```

</td><td valign="top">

```c
uchar sub_140035fd0(__int64 param1, int param2)
{
uchar buf_30[0x20];
uchar buf_50[0x20];
uchar buf_70[0x20];
uchar buf_90[0x20];
uint64 var_d0;
uint64 var_e0;
uint64 result0;
uint64 result1;
uint64 result2;
uint64 result3;
result0 = sub_14003a860(param2, *(uint32 *)*(uint64 *)(param1 + 0x8) >> 0xa & 0x3, param2);
var_d0 = result0;
var_e0 = &buf_30;
result1 = sub_140041b10(&buf_30, param1 + 0x10);
result2 = sub_140041a28(&buf_50, param1 + 0x30);
result3 = sub_140041bc4(&buf_70, result2, result1);
sub_14003eeb4(&var_d0, *(uint64 *)param1, result0, HIDWORD(var_d0), *(uint64 *)(param1 + 0x8), result3);
sub_140029310(&buf_90);
sub_140045f14(&buf_70);
return 0x1;
}
```

</td></tr>
</table>

## Loops and branches

Short functions with real control flow.

<a id="sub_1400168f0"></a>

### 4. `sub_1400168f0`

C line 2478 · asm line 29338 · 2 loops · 3 branches · 30 asm → 30 C lines

<table>
<tr><th>Assembly</th><th>Decompiled C</th></tr>
<tr><td valign="top">

```nasm
 movsxd r8, dword ptr [rcx+0x3C]
 xor r9d, r9d
 add r8, rcx
 movzx eax, word ptr [r8+0x14]
 movzx r10d, word ptr [r8+0x06]
 add rax, 0x18
 add rax, r8
 test r10d, r10d
 jz 0x0000000140016930

0x140016910:
 mov r8d, [rax+0x0C]
 cmp rdx, r8
 jb 0x0000000140016924
 mov ecx, [rax+0x08]
 add ecx, r8d
 cmp rdx, rcx
 jb 0x0000000140016932

0x140016924:
 inc r9d
 add rax, 0x28
 cmp r9d, r10d
 jb 0x0000000140016910

0x140016930:
 xor eax, eax

0x140016932:
 ret
```

</td><td valign="top">

```c
__int64 sub_1400168f0(__int64 param1, __int64 param2)
{
int vv1;
uint32 vv2;
ushort vv4;
uint64 vv5;
uint32 vv6;
vv1 = *(int *)(param1 + 0x3c);
vv2 = 0x0;
vv4 = *(ushort *)(vv1 + param1 + 0x6);
vv5 = *(ushort *)(vv1 + param1 + 0x14) + 0x18 + vv1 + param1;
if (vv4 == 0x0)
{
    return 0x0;
}
do {
    vv6 = *(uint32 *)(vv5 + 0xc);
    if ((unsigned __int64)param2 >= vv6)
    {
        if ((unsigned __int64)param2 < *(uint32 *)(vv5 + 0x8) + vv6)
        {
            return vv5;
        }
    }
    vv2 = vv2 + 0x1;
    vv5 = vv5 + 0x28;
}
while (vv2 < vv4);
return 0x0;
}
```

</td></tr>
</table>

<a id="sub_1400272f4"></a>

### 5. `sub_1400272f4`

C line 7170 · asm line 53501 · 2 loops · 5 branches · 29 asm → 42 C lines

<table>
<tr><th>Assembly</th><th>Decompiled C</th></tr>
<tr><td valign="top">

```nasm
 mov rax, rcx
 mov ecx, 0x7FFFFFFE
 test rdx, rdx
 jz 0x0000000140027325

0x140027301:
 test rcx, rcx
 jz 0x0000000140027325
 movzx r8d, word ptr [r9]
 test r8w, r8w
 jz 0x0000000140027325
 mov [rax], r8w
 add r9, 0x02
 add rax, 0x02
 dec rcx
 sub rdx, 0x01
 jnz 0x0000000140027301

0x140027325:
 lea rcx, [rax-0x02]
 test rdx, rdx
 cmovnz rcx, rax
 xor eax, eax
 mov [rcx], ax
 xor ecx, ecx
 test rdx, rdx
 mov eax, 0x8007007A
 cmovnz eax, ecx
 ret
```

</td><td valign="top">

```c
int sub_1400272f4(__int64 param1, __int64 param2, __int64 param4)
{
uint64 vv1;
uint64 vv2;
ushort vv3;
uint64 vv4;
uint32 vv5;
vv1 = param1;
vv2 = 0x7ffffffe;
if (param2 != 0x0)
{
    do {
        if (vv2 == 0x0)
        {
            break;
        }
        vv3 = *(ushort *)param4;
        if (vv3 == 0x0)
        {
            break;
        }
        *(ushort *)vv1 = vv3;
        param4 = param4 + 0x2;
        vv1 = vv1 + 0x2;
        vv2 = vv2 - 0x1;
        param2 = param2 - 0x1;
    }
    while (param2 != 0x0);
}
vv4 = vv1 - 0x2;
if (param2 != 0x0)
{
    vv4 = vv1;
}
*(ushort *)vv4 = 0x0;
vv5 = 0x8007007a;
if (param2 != 0x0)
{
    vv5 = 0x0;
}
return vv5;
}
```

</td></tr>
</table>

<a id="sub_140031a5c"></a>

### 6. `sub_140031a5c`

C line 12148 · asm line 68195 · 2 loops · 4 branches · 67 asm → 46 C lines

<table>
<tr><th>Assembly</th><th>Decompiled C</th></tr>
<tr><td valign="top">

```nasm

 push rbx
 push rsi
 push rdi
 push r14
 sub rsp, 0x38
 mov rax, [0x0000000140064200]
 xor rax, rsp
 mov [rsp+0x28], rax
 mov r14, rcx
 xor ebx, ebx
 mov [rsp+0x20], rbx
 add rcx, 0x08
 call _AcquireSRWLockExclusive
 mov rdi, [r14]
 lea rcx, [r14+0x08]
 test rdi, rdi
 jz 0x0000000140031AE9
 mov rbx, rdi
 mov [rsp+0x20], rbx
 lock inc [rdi]
 call _ReleaseSRWLockExclusive
 mov eax, [rdi+0x04]
 lea rax, [rax*8]
 lea rsi, [rdi+0x08]
 add rsi, rax
 add rdi, 0x08
 test rax, rax
 jz 0x0000000140031AEF

0x140031abf:
 mov rcx, rdi
 call sub_140031f40
 test al, al
 jnz 0x0000000140031ADE
 mov rcx, [rdi]
 call _EncodePointer
 mov rdx, rax
 mov rcx, r14
 call sub_140030d10

0x140031ade:
 add rdi, 0x08
 cmp rdi, rsi
 jnz 0x0000000140031ABF
 jmp 0x0000000140031AEF

0x140031ae9:
 call _ReleaseSRWLockExclusive
 nop

0x140031aef:
 test rbx, rbx
 jz 0x0000000140031AFE
 lea rcx, [local_1]
 call sub_1400317f4

0x140031afe:
 mov rcx, [rsp+0x28]
 xor rcx, rsp
 call 0x00000001400121C0
 add rsp, 0x38
 pop r14
 pop rdi
 pop rsi
 pop rbx
 ret
```

</td><td valign="top">

```c
__int64 sub_140031a5c(__int64 param1)
{
uint64 var_20;
uint64 vv1;
uint64 vv2;
uint64 vv4;
uint64 vv6;
uint64 vv7;
uint64 result3;
vv1 = 0x0;
var_20 = vv1;
_AcquireSRWLockExclusive(param1 + 0x8);
vv2 = *(uint64 *)param1;
if (vv2 != 0x0)
{
    vv1 = vv2;
    var_20 = vv1;
    *(uint32 *)vv2 = *(uint32 *)vv2 + 0x1;
    _ReleaseSRWLockExclusive(param1 + 0x8);
    vv4 = (uint64)*(uint32 *)(vv2 + 0x4) * 0x8;
    vv6 = vv2 + 0x8 + vv4;
    vv7 = vv2 + 0x8;
    if (vv4 != 0x0)
    {
        do {
            vv4 = sub_140031f40(vv7);
            if ((uchar)vv4 == 0x0)
            {
                result3 = _EncodePointer(*(uint64 *)vv7);
                vv4 = sub_140030d10(param1, result3);
            }
            vv7 = vv7 + 0x8;
        }
        while (vv7 != vv6);
    }
}
else
{
    vv4 = _ReleaseSRWLockExclusive();
}
if (vv1 != 0x0)
{
    vv4 = sub_1400317f4(&var_20);
}
return vv4;
}
```

</td></tr>
</table>

<a id="sub_1400387b4"></a>

### 7. `sub_1400387b4`

C line 15943 · asm line 78986 · 2 loops · 2 branches · 30 asm → 31 C lines

<table>
<tr><th>Assembly</th><th>Decompiled C</th></tr>
<tr><td valign="top">

```nasm
 arg_1 : byte ; [rsp+0x28]

 movsxd rax, r9d
 lea r10, [0x0000000140052410]           ; 0123456789ABCDEF
 add rdx, rax
 mov r9d, 0x01
 cmp byte ptr [arg_1], 0x00
 lea rax, [0x000000014004C840]           ; 0123456789abcdef
 cmovz r10, rax
 shl r9d, cl

0x1400387da:
 lea eax, [r9-0x01]
 and eax, r8d
 cmp ecx, 0x04
 jnl 0x00000001400387EA
 add al, 0x30
 jmp 0x00000001400387EF

0x1400387ea:
 movzx eax, byte ptr [r10+rax*1]

0x1400387ef:
 dec rdx
 shr r8d, cl
 mov [rdx], al
 test r8d, r8d
 jnz 0x00000001400387DA
 mov rax, rdx
 ret
```

</td><td valign="top">

```c
__int64 sub_1400387b4(int param1, __int64 param2, int param3, int param4, uchar param5)
{
uint64 vv2;
uint64 vv3;
uint32 vv5;
uint32 vv6;
uchar vv7;
vv2 = &mem_140052410;
vv3 = param2 + param4;
if (param5 == 0x0)
{
    vv2 = &mem_14004c840;
}
do {
    vv5 = (0x1 << param1) - 0x1;
    vv6 = vv5 & param3;
    if (param1 < 0x4)
    {
        vv7 = (uchar)(vv6 + 0x30);
    }
    else
    {
        vv7 = *(uchar *)(vv2 + vv6);
    }
    vv3 = vv3 - 0x1;
    param3 = (unsigned int)param3 >> param1;
    *(uchar *)vv3 = vv7;
}
while (param3 != 0x0);
return vv3;
}
```

</td></tr>
</table>

<a id="sub_140038800"></a>

### 8. `sub_140038800`

C line 15978 · asm line 79022 · 2 loops · 2 branches · 35 asm → 33 C lines

<table>
<tr><th>Assembly</th><th>Decompiled C</th></tr>
<tr><td valign="top">

```nasm
 arg_1 : byte ; [rsp+0x28]

 mov [rsp+0x08], rbx
 movsxd rax, r9d
 lea r11, [0x0000000140052410]           ; 0123456789ABCDEF
 add rdx, rax
 movsxd r10, ecx
 cmp byte ptr [arg_1], 0x00
 lea rax, [0x000000014004C840]           ; 0123456789abcdef
 mov ecx, r10d
 mov r9d, 0x01
 cmovz r11, rax
 shl r9d, cl

0x140038831:
 lea eax, [r9-0x01]
 and eax, r8d
 cmp r10d, 0x04
 jnl 0x0000000140038842
 add al, 0x30
 jmp 0x0000000140038847

0x140038842:
 movzx eax, byte ptr [r11+rax*1]

0x140038847:
 dec rdx
 mov rcx, r10
 shr r8, cl
 mov [rdx], al
 test r8, r8
 jnz 0x0000000140038831
 mov rbx, [rsp+0x08]
 mov rax, rdx
 ret
```

</td><td valign="top">

```c
__int64 sub_140038800(int param1, __int64 param2, __int64 param3, int param4, uchar param5)
{
uint64 vv2;
uint64 vv3;
int vv4;
uint32 vv6;
uint32 vv7;
uchar vv8;
vv2 = &mem_140052410;
vv3 = param2 + param4;
vv4 = param1;
if (param5 == 0x0)
{
    vv2 = &mem_14004c840;
}
do {
    vv6 = (0x1 << vv4) - 0x1;
    vv7 = vv6 & (uint32)param3;
    if (vv4 < 0x4)
    {
        vv8 = (uchar)(vv7 + 0x30);
    }
    else
    {
        vv8 = *(uchar *)(vv2 + vv7);
    }
    vv3 = vv3 - 0x1;
    param3 = (unsigned __int64)param3 >> vv4;
    *(uchar *)vv3 = vv8;
}
while (param3 != 0x0);
return vv3;
}
```

</td></tr>
</table>

<a id="sub_140038860"></a>

### 9. `sub_140038860`

C line 16015 · asm line 79063 · 2 loops · 2 branches · 44 asm → 33 C lines

<table>
<tr><th>Assembly</th><th>Decompiled C</th></tr>
<tr><td valign="top">

```nasm
 sub rsp, 0x18
 mov rax, [0x0000000140064200]
 xor rax, rsp
 mov [rsp+0x08], rax
 lea r11, [0x00000001400526EA]           ; 0001020304050607
 mov r9d, edx
 cmp edx, 0x64
 jb 0x00000001400388A9

0x140038882:
 add r8d, 0xFFFFFFFE
 mov eax, 0x51EB851F
 mul r9d
 shr edx, 0x05
 imul eax, edx, 0x64
 sub r9d, eax
 movzx eax, word ptr [r11+r9*2]
 mov r9d, edx
 mov [rcx+r8*1], ax
 cmp edx, 0x64
 jnb 0x0000000140038882

0x1400388a9:
 cmp r9d, 0x0A
 jb 0x00000001400388C2
 mov eax, r9d
 add r8d, 0xFFFFFFFE
 movzx eax, word ptr [r11+rax*2]
 mov [r8+rcx*1], ax
 jmp 0x00000001400388CD

0x1400388c2:
 dec r8d
 add r9b, 0x30
 mov [r8+rcx*1], r9b

0x1400388cd:
 mov eax, r8d
 add rax, rcx
 mov rcx, [rsp+0x08]
 xor rcx, rsp
 call 0x00000001400121C0
 add rsp, 0x18
 ret
```

</td><td valign="top">

```c
__int64 sub_140038860(__int64 param1, int param2, __int64 param3)
{
uint32 vv1;
uint32 vv2;
uint32 vv3;
uint32 vv4;
uint32 vv5;
vv1 = param2;
if ((unsigned int)param2 >= 0x64)
{
    do {
        param3 = (uint32)param3 - 0x2;
        vv2 = 0x51eb851f;
        vv3 = (uint32)(__emulu(0x51eb851f, vv1) >> 0x20);
        vv2 = (vv3 >> 0x5) * 0x64;
        vv4 = *(ushort *)((vv1 - vv2) * 0x2 + (char *)&mem_1400526ea);
        vv1 = vv3 >> 0x5;
        *(ushort *)(param1 + param3) = vv4;
    }
    while (vv3 >> 0x5 >= 0x64);
}
if (vv1 >= 0xa)
{
    vv5 = (uint32)param3 - 0x2;
    *(ushort *)(vv5 + param1) = *(ushort *)(vv1 * 0x2 + (char *)&mem_1400526ea);
}
else
{
    vv5 = (uint32)param3 - 0x1;
    *(uchar *)(vv5 + param1) = (uchar)vv1 + 0x30;
}
return vv5 + param1;
}
```

</td></tr>
</table>

<a id="sub_1400388e8"></a>

### 10. `sub_1400388e8`

C line 16052 · asm line 79116 · 2 loops · 2 branches · 54 asm → 39 C lines

<table>
<tr><th>Assembly</th><th>Decompiled C</th></tr>
<tr><td valign="top">

```nasm
 mov [rsp+0x08], rbx
 mov [rsp+0x10], rsi
 push rdi
 sub rsp, 0x20
 mov rsi, rcx
 mov edi, r8d
 mov rcx, rdx
 mov rbx, rdx
 call sub_140048104
 lea r9, [0x00000001400526EA]            ; 0001020304050607
 cmp rbx, 0x64
 jb 0x0000000140038953
 mov r10, 0x47AE147AE147AE15

0x14003891f:
 mov r8, rbx
 mov rax, r10
 mul rbx
 add edi, 0xFFFFFFFE
 sub r8, rdx
 shr r8, 0x01
 add r8, rdx
 shr r8, 0x06
 imul rax, r8, 0x64
 sub rbx, rax
 mov eax, ebx
 mov rbx, r8
 movzx eax, word ptr [r9+rax*2]
 mov [rsi+rdi*1], ax
 cmp r8, 0x64
 jnb 0x000000014003891F

0x140038953:
 cmp rbx, 0x0A
 jb 0x0000000140038969
 mov eax, ebx
 add edi, 0xFFFFFFFE
 movzx eax, word ptr [r9+rax*2]
 mov [rdi+rsi*1], ax
 jmp 0x0000000140038971

0x140038969:
 dec edi
 add bl, 0x30
 mov [rdi+rsi*1], bl

0x140038971:
 mov rbx, [rsp+0x30]
 mov eax, edi
 add rax, rsi
 mov rsi, [rsp+0x38]
 add rsp, 0x20
 pop rdi
 ret
```

</td><td valign="top">

```c
__int64 sub_1400388e8(__int64 param1, __int64 param2, int param3)
{
uint32 vv1;
uint64 vv2;
uint64 vv4;
uint64 vv5;
uint64 vv6;
uint32 vv8;
uint32 vv10;
uint32 vv11;
vv1 = param3;
vv2 = param2;
sub_140048104(param2);
if (vv2 >= 0x64)
{
    do {
        vv4 = vv2;
        vv5 = __umulh(0x47ae147ae147ae15, vv2);
        vv1 = vv1 - 0x2;
        vv6 = (vv4 - vv5 >> 0x1) + vv5 >> 0x6;
        vv8 = vv2 - vv6 * 0x64;
        vv2 = vv6;
        *(ushort *)(param1 + vv1) = *(ushort *)(vv8 * 0x2 + (char *)&mem_1400526ea);
    }
    while (vv6 >= 0x64);
}
if (vv2 >= 0xa)
{
    vv10 = vv1 - 0x2;
    vv11 = *(ushort *)((uint32)vv2 * 0x2 + (char *)&mem_1400526ea);
    *(ushort *)(vv10 + param1) = vv11;
}
else
{
    vv10 = vv1 - 0x1;
    *(uchar *)(vv10 + param1) = (uchar)vv2 + 0x30;
}
return vv10 + param1;
}
```

</td></tr>
</table>

<a id="sub_14003b5bc"></a>

### 11. `sub_14003b5bc`

C line 17357 · asm line 83183 · 2 loops · 5 branches · 52 asm → 43 C lines

<table>
<tr><th>Assembly</th><th>Decompiled C</th></tr>
<tr><td valign="top">

```nasm
 push rbx
 push rbp
 push rsi
 push rdi
 mov r11, [rcx]
 xor r9d, r9d
 mov r10, r11
 mov ebp, 0x30

0x14003b5cf:
 movzx eax, word ptr [r10]
 mov rdi, r10
 mov esi, r9d
 add r10, 0x02
 lea r9d, [r9+r9*4]
 lea r9d, [r9-0x18]
 lea r9d, [rax+r9*2]
 cmp r10, rdx
 jz 0x000000014003B5FD
 movzx eax, word ptr [r10]
 cmp bp, ax
 jnbe 0x000000014003B5FD
 cmp ax, 0x39
 jbe 0x000000014003B5CF

0x14003b5fd:
 mov [rcx], r10
 mov rax, r10
 sub rax, r11
 mov rcx, rax
 sar rcx, 0x01
 cmp rcx, 0x09
 jle 0x000000014003B630
 cmp rax, 0x14
 jnz 0x000000014003B62D
 movzx eax, word ptr [rdi]
 lea rcx, [rsi+rsi*4]
 sub eax, ebp
 lea rax, [rax+rcx*2]
 cmp rax, 0x7FFFFFFF
 jbe 0x000000014003B630

0x14003b62d:
 mov r9d, r8d

0x14003b630:
 mov eax, r9d
 pop rdi
 pop rsi
 pop rbp
 pop rbx
 ret
```

</td><td valign="top">

```c
int sub_14003b5bc(__int64 param1, __int64 param2, int param3)
{
__int64 vv1;
uint32 vv2;
__int64 vv3;
ushort vv5;
uint64 vv6;
uint32 vv7;
ushort vv10;
vv1 = *(uint64 *)param1;
vv2 = 0x0;
vv3 = vv1;
do {
    vv5 = *(ushort *)vv3;
    vv6 = vv3;
    vv7 = vv2;
    vv3 = vv3 + 0x2;
    vv2 = (vv2 * 0x4 + vv2 - 0x18) * 0x2 + vv5;
    if (vv3 == param2)
    {
        break;
    }
    vv10 = *(ushort *)vv3;
    if ((ushort)0x30 > vv10)
    {
        break;
    }
}
while (vv10 <= 0x39);
*(uint64 *)param1 = vv3;
if (vv3 - vv1 >> 0x1 > 0x9)
{
    if (vv3 - vv1 == 0x14)
    {
        if (((uint64)vv7 * 0x4 + vv7) * 0x2 + (*(ushort *)vv6 - 0x30) <= 0x7fffffff)
        {
            return vv2;
        }
    }
    vv2 = param3;
}
return vv2;
}
```

</td></tr>
</table>

<a id="sub_140044210"></a>

### 12. `sub_140044210`

C line 21549 · asm line 95805 · 2 loops · 3 branches · 55 asm → 37 C lines

<table>
<tr><th>Assembly</th><th>Decompiled C</th></tr>
<tr><td valign="top">

```nasm
 arg_1 : qword ; [rsp+0x38]

 mov [rsp+0x18], rbx
 push rdi
 sub rsp, 0x20
 mov eax, edx
 mov rbx, rcx
 cdq
 and edx, 0x1F
 add eax, edx
 mov r8d, eax
 and eax, 0x1F
 sar r8d, 0x05
 sub eax, edx
 add [rcx+0xA0], r8d
 mov edi, eax
 test eax, eax
 jz 0x000000014004429B
 mov r10, [rcx+0x08]
 test r10, r10
 jz 0x000000014004429B
 mov r9d, 0x20
 mov [rsp+0x30], rsi
 sub r9d, eax
 xor r11d, r11d
 xor esi, esi

0x14004425a:
 mov rdx, [rbx]
 mov ecx, r9d
 mov eax, [rdx+r11*4]
 mov r8d, eax
 shr r8d, cl
 mov ecx, edi
 shl eax, cl
 add eax, esi
 mov [rsp+0x38], r8d
 mov [rdx+r11*4], eax
 mov esi, r8d
 inc r11
 cmp r11, r10
 jb 0x000000014004425A
 mov rsi, [rsp+0x30]
 test r8d, r8d
 jz 0x000000014004429B
 lea rdx, [arg_1]
 mov rcx, rbx
 call sub_140049484

0x14004429b:
 mov rax, rbx
 mov rbx, [rsp+0x40]
 add rsp, 0x20
 pop rdi
 ret
```

</td><td valign="top">

```c
__int64 sub_140044210(__int64 param1, int param2)
{
uint32 var_38;
uint32 vv1;
uint64 vv2;
uint64 vv4;
uint32 vv5;
uint64 vv6;
uint32 vv7;
uint32 vv8;
vv1 = param2 >> 0x1f;
*(uint32 *)(param1 + 0xa0) = *(uint32 *)(param1 + 0xa0) + ((int)(param2 + (vv1 & 0x1f)) >> 0x5);
if ((param2 + (vv1 & 0x1f) & 0x1f) - (vv1 & 0x1f) != 0x0)
{
    vv2 = *(uint64 *)(param1 + 0x8);
    if (vv2 != 0x0)
    {
        vv4 = 0x0;
        vv5 = 0x0;
        do {
            vv6 = *(uint64 *)param1;
            vv7 = *(uint32 *)(vv4 * 0x4 + vv6);
            vv8 = vv7 >> 0x20 - ((param2 + (vv1 & 0x1f) & 0x1f) - (vv1 & 0x1f));
            var_38 = vv8;
            *(uint32 *)(vv4 * 0x4 + vv6) = (vv7 << (param2 + (vv1 & 0x1f) & 0x1f) - (vv1 & 0x1f)) + vv5;
            vv5 = vv8;
            vv4 = vv4 + 0x1;
        }
        while (vv4 < vv2);
        if (vv8 != 0x0)
        {
            sub_140049484(param1, &var_38, vv8);
        }
    }
}
return param1;
}
```

</td></tr>
</table>

<a id="sub_14004711c"></a>

### 13. `sub_14004711c`

C line 22497 · asm line 99674 · 2 loops · 3 branches · 21 asm → 32 C lines

<table>
<tr><th>Assembly</th><th>Decompiled C</th></tr>
<tr><td valign="top">

```nasm
 mov r10, [rcx+0x18]
 xor eax, eax
 mov r8, [rcx+0x10]
 mov r9, 0x8000000000000000
 cmp r8, r10
 jz 0x0000000140047156

0x140047135:
 mov rcx, [r8]
 mov rdx, [rcx+0x50]
 cmp rdx, r9
 cmovnle rax, rcx
 add r8, 0x10
 cmp rdx, r9
 cmovle rdx, r9
 mov r9, rdx
 cmp r8, r10
 jnz 0x0000000140047135

0x140047156:
 ret
```

</td><td valign="top">

```c
__int64 sub_14004711c(__int64 param1)
{
uint64 vv1;
uint64 vv2;
uint64 vv3;
__int64 vv4;
uint64 vv5;
__int64 vv6;
vv1 = *(uint64 *)(param1 + 0x18);
vv2 = 0x0;
vv3 = *(uint64 *)(param1 + 0x10);
vv4 = -0x8000000000000000;
if (vv3 != vv1)
{
    do {
        vv5 = *(uint64 *)vv3;
        vv6 = *(uint64 *)(vv5 + 0x50);
        if (vv6 > vv4)
        {
            vv2 = vv5;
        }
        vv3 = vv3 + 0x10;
        if (vv6 <= vv4)
        {
            vv6 = vv4;
        }
        vv4 = vv6;
    }
    while (vv3 != vv1);
}
return vv2;
}
```

</td></tr>
</table>

<a id="sub_140047cbc"></a>

### 14. `sub_140047cbc`

C line 22861 · asm line 100605 · 2 loops · 2 branches · 44 asm → 36 C lines

<table>
<tr><th>Assembly</th><th>Decompiled C</th></tr>
<tr><td valign="top">

```nasm
 arg_1 : qword ; [rsp+0x30]

 mov [rsp+0x20], rbp
 push rsi
 sub rsp, 0x20
 mov ebp, [rcx+0xA0]
 mov rsi, rcx
 sub ebp, [rdx+0xA0]
 test ebp, ebp
 jle 0x0000000140047D31
 mov [rsp+0x38], rbx
 mov ebx, [rcx+0x08]
 mov [rsp+0x40], rdi
 lea edi, [rbx+rbp*1]
 mov edx, edi
 call sub_140049bd0
 dec edi
 sub ebx, 0x01
 js 0x0000000140047D0A

0x140047cf7:
 mov rdx, [rsi]
 movsxd rcx, edi
 dec edi
 mov eax, [rdx+rbx*4]
 sub ebx, 0x01
 mov [rdx+rcx*4], eax
 jns 0x0000000140047CF7

0x140047d0a:
 mov rcx, [rsi]
 lea r8, [arg_1]
 mov edx, ebp
 mov dword ptr [arg_1], 0x00
 call sub_140039350
 sub [rsi+0xA0], ebp
 mov rdi, [rsp+0x40]
 mov rbx, [rsp+0x38]

0x140047d31:
 mov rbp, [rsp+0x48]
 add rsp, 0x20
 pop rsi
 ret
```

</td><td valign="top">

```c
void sub_140047cbc(__int64 param1, __int64 param2)
{
uint32 var_30;
int vv2;
uint32 vv3;
uint32 vv4;
int vv5;
uint32 vv6;
uint64 vv7;
int vv8;
uint32 vv9;
vv2 = *(uint32 *)(param1 + 0xa0) - *(uint32 *)(param2 + 0xa0);
if (vv2 > 0x0)
{
    vv3 = *(uint32 *)(param1 + 0x8);
    vv4 = vv2 + vv3;
    sub_140049bd0(param1, vv4);
    vv5 = vv4 - 0x1;
    vv6 = vv3 - 0x1;
    if ((int)vv6 >= 0x0)
    {
        do {
            vv7 = *(uint64 *)param1;
            vv8 = vv5;
            vv5 = vv5 - 0x1;
            vv9 = *(uint32 *)(vv6 * 0x4 + vv7);
            vv6 = vv6 - 0x1;
            *(uint32 *)(vv8 * 0x4 + vv7) = vv9;
        }
        while ((int)vv6 >= 0x0);
    }
    var_30 = 0x0;
    sub_140039350(*(uint64 *)param1, vv2, &var_30);
    *(uint32 *)(param1 + 0xa0) = *(uint32 *)(param1 + 0xa0) - vv2;
}
}
```

</td></tr>
</table>

<a id="sub_140047f58"></a>

### 15. `sub_140047f58`

C line 22990 · asm line 100855 · 2 loops · 3 branches · 56 asm → 29 C lines

<table>
<tr><th>Assembly</th><th>Decompiled C</th></tr>
<tr><td valign="top">

```nasm

 mov [rsp+0x18], rbx
 mov [rsp+0x20], rsi
 push rdi
 sub rsp, 0x30
 mov rax, [0x0000000140064200]
 xor rax, rsp
 mov [rsp+0x28], rax
 mov esi, edx
 mov rdi, rcx
 test edx, edx
 jnz 0x0000000140047F8B
 mov edx, 0x01
 call sub_140038424
 jmp 0x0000000140047FDC

0x140047f8b:
 mov edx, 0x05
 mov dword ptr [local_1], 0x00
 bsr ebx, esi
 call sub_140038424
 xor ebx, 0x1F
 mov ecx, 0x1F
 sub ecx, ebx
 mov ebx, 0x01
 shl ebx, cl
 sar ebx, 0x01
 jz 0x0000000140047FD2

0x140047fb5:
 mov rcx, rdi
 call sub_140049974
 test ebx, esi
 jz 0x0000000140047FCE
 mov edx, 0x05
 mov rcx, rdi
 call sub_1400490a0

0x140047fce:
 sar ebx, 0x01
 jnz 0x0000000140047FB5

0x140047fd2:
 mov edx, esi
 mov rcx, rdi
 call sub_140044210

0x140047fdc:
 mov rcx, [rsp+0x28]
 xor rcx, rsp
 call 0x00000001400121C0
 mov rbx, [rsp+0x50]
 mov rsi, [rsp+0x58]
 add rsp, 0x30
 pop rdi
 ret
```

</td><td valign="top">

```c
int sub_140047f58(__int64 param1, int param2, int param3, int param4)
{
int vv1;
int vv4;
uint32 result0;
uint32 result4;
if (param2 == 0x0)
{
    result0 = sub_140038424(param1, 0x1);
    return result0;
}
vv1 = __bsr((uint32)param2);
sub_140038424(param1, 0x5, param3, param4, 0x0);
vv4 = 0x1 << 0x1f - (vv1 ^ 0x1f) >> 0x1;
if (vv4 != 0x0)
{
    do {
        sub_140049974(param1);
        if ((vv4 & param2) != 0x0)
        {
            sub_1400490a0(param1, 0x5);
        }
        vv4 = vv4 >> 0x1;
    }
    while (vv4 != 0x0);
}
result4 = sub_140044210(param1, param2);
return result4;
}
```

</td></tr>
</table>

---

Generated from WindowsTerminal.asm and WindowsTerminal.c, produced by arkDasm 1.3.0
