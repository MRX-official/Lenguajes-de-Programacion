# Operaciones con expresiones regulares
> Una expresión regular (o RE, por sus siglas en inglés) especifica un conjunto de cadenas que coinciden con ella; las funciones de este módulo permiten comprobar si una determinada cadena coincide con una expresión regular dada (o si una expresión regular dada coincide con una determinada cadena, que se reduce a lo mismo).
> Las expresiones regulares usan el carácter de barra inversa ('\') para indicar formas especiales o para permitir el uso de caracteres especiales sin invocar su significado especial. Esto choca con el uso de Python de este carácter para el mismo propósito con los literales de cadena.
## Metacaracteres
Los metacaracteres son carateres con un significado especial:
| Metacaracter | Descripción | Ejemplo |
| --- | --- | --- |
| [ ] | Un conjunto de caracteres |"[a-m]"|
| \ | Señala una secuencia especial (también se puede usar para escapar de caracteres especiales) |"\d"|
| . | Cualquier carácter (excepto el carácter de nueva línea) |"he..o"|
| ^ | Comienza con |"^hello"|
| $ | Termina con |"world$"|
| * | Cero o más ocurrencias |"aix*"|
| + | Una o más ocurrencias |"aix+"|
| {} | Exactamente el número especificado de ocurrencias |"al{2}"|
| PIPE | Cualquiera o |"falls(PIPE)stays"|
| ( ) | Capturar y agurpar ||

PIPE= "|"
## Sintaxis de expresiones regulares
Cubriremos dos funciones importantes, que se usarían para manejar expresiones regulares. Pero primero una pequeña cosa: hay varios caracteres, que tendrían un significado especial cuando se usan en expresiones regulares. Para evitar cualquier confusión al tratar con expresiones regulares, usaríamos Raw Strings como r'expression '.
### Funcion search
Esta función busca la primera aparición del patrón RE dentro de una cadena con banderas opcionales.
```
re.search(pattern, string, flags=0)
```
### Funcion match
Esta función intenta hacer coincidir el patrón RE con la cadena con banderas opcionales.
```
re.match(pattern, string, flags=0)
```
* Pattern: Ésta es la expresión regular que debe coincidir.
* String: Esta es la cadena, que se buscará para que coincida con el patrón al principio de la cadena.
* Flags: Puede especificar diferentes banderas usando OR bit a bit (|). Estos son modificadores.
#### Modificadores
* group(num=0):Este método devuelve una coincidencia completa (o un número de subgrupo específico)
* groups():Este método devuelve todos los subgrupos coincidentes en una tupla (vacío si no había ninguno)

Hay que tener en cuenta que los patrones que empiezan con aserciones positivas de búsqueda tardía no coincidirán con el principio de la cadena que se está buscando; lo más probable es que se quiera usar la función search() en lugar de la función match():
```
import re
m = re.search('(?<=abc)def', 'abcdef')
m.group(0)
'def'
```
## Ejemplo:
```
import re

line = "Cats are smarter than dogs"

matchObj = re.match( r'(.*) are (.*?) .*', line, re.M|re.I)

if matchObj:
   print "matchObj.group() : ", matchObj.group()
   print "matchObj.group(1) : ", matchObj.group(1)
   print "matchObj.group(2) : ", matchObj.group(2)
else:
   print "No match!!"
```
## Ejemplo 2
```
#Importando el modulo regex 
import re
#compilando la regex
patron=re.compile(r'\bfoo\b') #busca la palabra foo

# Entrada
texto = """ bar foo bar foo barbarfoo foofoo foo bar"""

#match nos devuelve None porque no hubo coincidencia al comienzo del texto
print(patron.match(texto))

#match encuentra una coincidencia en el comienzo del texto
m= patron.match("foo bar")
print(m)

#search nos devuelve la coincidencia en cualquier ubicacion
s=patron.search(texto)
print(s)
```
## Referencias
* [w3schools](https://www.w3schools.com/python/gloss_python_regex_metacharacters.asp)
* [tutorialspoint](https://www.tutorialspoint.com/python/python_reg_expressions.htm)
