### ASCII


ASCII es una forma de cifrado estándar de 7-bits que te permite escribir texto en números entre el 0 hasta el 127

En python, 
*  la función char()
  
     ASCII  ---> TEXT

*  la función ord():

   TEXT ---> ASCII

### Hexadecimal

Los el cifrado ASCII puede ser representado en Hexadecimal, esto sucede después del proceso de cifrado del texto a ASCII, a partir de aquí cada número decimal se convierte a su equivalen en Hexadecimal.
sometimes, when we try to share the cyphertext a few bytes cannot be found in the ASCII table so they cant printable. in that cases the use hex numbers to do the job. grabbing the first letter to transform in the ASCII decimal equivalent and then that numbers its convert in his hex. with the help of python and the `.hex()` instance method we can see this in action:
```python
x= b'crypto{You_will_be_working_with_hex_strings_a_lot}'
y= x.hex()
print(y)
```
so we can get the result running this python script:
```bash
❯ python bytestohex.py
63727970746f7b596f755f77696c6c5f62655f776f726b696e675f776974685f6865785f737472696e67735f615f6c6f747d
```
and to get it back we use the `bytes.fromhex()` function to get it back:
```python
x = "63727970746f7b596f755f77696c6c5f62655f776f726b696e675f776974685f6865785f737472696e67735f615f6c6f747d"
y = bytes.fromhex(x)
print(y)
```
```bash
❯ python hextringsconverter.py 
b'crypto{You_will_be_working_with_hex_strings_a_lot}'
```
### Base64

the base64 format helps us to represent binary data as an ASCII string using a 64 alfabet
Base64 is most commonly used online, so binary data such as images can be easily included into HTML or CSS files.
in python, has a module call `base64` that help us to encoding and decoding binary data to and from base64 strings. 

in this exercise we have a hexstrings `72bca9b68fc16ac7beeb8f849dca1d8a783e8acf9679bf9269f7bf` and we need to decode in bytes and then encode to base 64. down below we can see the python code to help us with the solution

import the module to manage data in base64 format
```python
import base64
```

create a variable that contains our hexstring, in this case i assign X.
```python
X = "72bca9b68fc16ac7beeb8f849dca1d8a783e8acf9679bf9269f7bf"
```

After creating it we gonna convert that hexstring to bytes so the way we gonna do this is put the name of the format we gonna convert (in this case, bytes) 
and the we got (in this case hex) add the word from as we saw below to take effect
```python
Y = bytes.fromhex(X)
```

this step is optinal if you wanna see that this work
```python
print(Y)
```

so we got the byte form. the only thing we need is the base64 encoding so we gonna used the module that we import before (base64) and a function called b64encode
```python
print(base64.b64encode(Y))
```
NOTE: base6encode, recive bytes-like object as input and returns the base64-encoded data also as bytes object.

so we have the results of the python program that we created
```bash
b'r\xbc\xa9\xb6\x8f\xc1j\xc7\xbe\xeb\x8f\x84\x9d\xca\x1d\x8ax>\x8a\xcf\x96y\xbf\x92i\xf7\xbf'
b'crypto/Base+64+Encoding+is+Web+Safe/'
```
this is the final structure of our python base64 encoding python program
```python
import base64
X = "72bca9b68fc16ac7beeb8f849dca1d8a783e8acf9679bf9269f7bf"
Y = bytes.fromhex(X)
print(Y)
print(base64.b64encode(Y))
```
### MESSAGE TO NUMBERS
In cryptographic systems like RSA works on numbers to make the encryption of the messages. but those are characters so the most common way to convert numbers is take the text, extract their ASCII bytes and convert it to: 
base-16 (Hexadecimal)
or
base-10 (decimal)

like we can see in this example

```shell
message: HELLO
ascii bytes: [72, 69, 76, 76, 79]
hex bytes: [0x48, 0x45, 0x4c, 0x4c, 0x4f]
base-16: 0x48454c4c4f
base-10: 310400273487 
```

in this excercise we need to get the message back for this integer:
```shell
11515195063862318899931685488813747395775516287289682636499965282714637259206269
```
and they request us  to revert the encryption. so to do this first we need to identify the format of the message.
giving a quick view is a base10 string. after knowing this, only we need is convert it to bytes. to do this we got to
used the function `long_to_bytes()` as we see here:
```python
X= 11515195063862318899931685488813747395775516287289682636499965282714637259206269
print(long_to_bytes(X))
```
and as the resualt applying this we got the message decripted
```bash
b'crypto{3nc0d1n6_4ll_7h3_w4y_d0wn}'
```
###  XOR
|     A     |     B     |    Output     |
|:--------: |:-------:  | :------------:|
|     0     |     0     |       0       |
|     0     |     1     |       1       |
|     1     |     0     |       1       |
|     1     |     1     |       0       |
```python
x= "label"
y= 13
for pj in x:
  m=ord(pj)
  xor=m ^ y
  print(chr(xor), end="")
```
```bash
aloha
```
### XOR PROPERTIES
