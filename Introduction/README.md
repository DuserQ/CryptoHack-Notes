**ASCII**


ASCII es una forma de cifrado estándar de 7-bits que te permite escribir texto en números entre el 0 hasta el 127

En python, 
*  la función char()
  
     ASCII  ---> TEXT

*  la función ord():

   TEXT ---> ASCII

Los el cifrado ASCII puede ser representado en Hexadecimal, esto sucede después del proceso de cifrado del texto a ASCII, a partir de aquí cada número decimal se convierte a su equivalen en Hexadecimal.
sometimes, when we try to share the cyphertext a few bytes cannot be found in the ASCII table so they cant printable. in that cases the use hex numbers to do the job. grabbing the first letter to transform in the ASCII decimal equivalent and then that numbers its convert in his hex format like this
```python
x=b'crypto{You_will_be_working_with_hex_strings_a_lot}'
y= x.hex()
print(y)
``


