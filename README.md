# RETO 12
## Strings

Los ejercicios del repositorio 12 se encuentran en el archivo `notebook`.
## Punto 1:

### `endswith`

+ Método que devuelve `True` si una cadena termina con el sufijo especificado y `False` en caso contrario.

### `startswith`

+ Método que devuelve `True` si una cadena comienza con el prefijo especificado y `False` en caso contrario.

### `isalpha`

+ Método que devuelve `True` si todos los caracteres en una cadena son alfabéticos (letras) y la cadena no está vacía; de lo contrario, devuelve `False`.

### `isalnum`

+ Método que devuelve `True` si todos los caracteres en una cadena son alfanuméricos (letras o números) y la cadena no está vacía; de lo contrario, devuelve `False`.

### `isdigit`

+ Método que devuelve `True` si todos los caracteres en una cadena son dígitos y la cadena no está vacía; de lo contrario, devuelve `False`.

### `isspace`

+ Método que devuelve `True` si todos los caracteres en una cadena son espacios en blanco y la cadena no está vacía; de lo contrario, devuelve `False`.

### `istitle`

+ Método que devuelve `True` si la cadena sigue la convención de título, es decir, si la primera letra de cada palabra está en mayúscula y las demás letras están en minúscula; de lo contrario, devuelve `False`.

### `islower`

+ Método que devuelve `True` si todos los caracteres alfabéticos en una cadena están en minúscula y la cadena no está vacía; de lo contrario, devuelve `False`.

### `isupper`

+ Método que devuelve `True` si todos los caracteres alfabéticos en una cadena están en mayúscula y la cadena no está vacía; de lo contrario, devuelve `False`.

## Punto 2:
+ Cantidad de vocales
+ Cantidad de consonantes
+ Listado de las 50 palabras que más se repiten
```python
# Importa la clase Counter de la librería collections, que se utilizará para contar elementos.
from collections import Counter
# función llamada contar vocales y consonantes que toma un parámetro de texto.
def contar_vocales_y_consonantes(texto):
    # Inicializa contadores para las vocales y las consonantes.
    count_vocales = 0 
    count_consonantes = 0 
    # Itera sobre cada letra en el texto.
    for letra in texto:                                                      
        # Convierte la letra a minúsculas para realizar comparaciones sin distinción entre mayúsculas y minúsculas.
        letra_min = letra.lower()                                              
        # Comprueba si la letra (en minúsculas) es una vocal.
        if letra_min in "aeiouáéíóú":                                            
            count_vocales += 1                                                         
        # Comprueba si la letra (en minúsculas) es una consonante.
        elif letra_min in "bcdfghjklmnñpqrstvwxyz":                              
            count_consonantes += 1 
    # Imprime el número de vocales y consonantes.
    print("El número de vocales es: " + str(count_vocales)) 
    print("El número de consonantes es: " + str(count_consonantes)) 
# Define una función llamada palabras_mas_repetidas que toma un parámetro de texto.
def palabras_mas_repetidas(texto):
    # Divide el texto en palabras.
    palabras = texto.split()                                                    
    # Utiliza Counter para contar la frecuencia de cada palabra y obtiene las 50 palabras más comunes.
    palabras_repetidas = Counter(palabras).most_common(50)                              
    # Imprime las 50 palabras más repetidas.
    print("Las 50 palabras que más se repiten son: " + str(palabras_repetidas))
# Comprueba si este script es el programa principal que se está ejecutando.
if __name__ == "__main__":
    # Abre el archivo "mbox-short.txt" en modo de lectura y lo asocia con el identificador 'archivo'.
    with open("mbox-short.txt", "r") as archivo:                                     
        # Lee el contenido del archivo y lo asigna a la variable 'texto_archivo'.
        texto_archivo = archivo.read()                                                       
    # Llama a la función contar_vocales_y_consonantes con el texto del archivo como argumento.
    contar_vocales_y_consonantes(texto_archivo)                                                  
    # Llama a la función palabras_mas_repetidas con el texto del archivo como argumento.
    palabras_mas_repetidas(texto_archivo)
```
