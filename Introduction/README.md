**ASCII**


ASCII es una forma de cifrado estándar de 7-bits que te permite escribir texto en números entre el 0 hasta el 127

En python, 
*  la función char()
  
     ASCII  ---> TEXT

*  la función ord():

   TEXT ---> ASCII

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



