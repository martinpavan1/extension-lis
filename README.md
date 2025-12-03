✨ Extensiones del Lenguaje

Este proyecto agrega nuevas capacidades al lenguaje original mediante tres extensiones:

✔️ Operador ternario

✔️ += (azúcar sintáctico)

✔️ -= (azúcar sintáctico)

🧩 Operador Ternario (? :)
Permite seleccionar entre dos expresiones enteras según el valor de una expresión booleana.
Equivale al if de una sola línea.

Sintaxis:
intexp ::= boolexp '?' intexp ':' intexp


Ejemplo:
x := 5
true ? x := 20 : x := 10
-- valor final de x = 20

➕ Azúcar Sintáctico: +=
Expresión corta equivalente a x = x + e.

Sintaxis:
comm ::= var '+=’ intexp ';'

Ejemplo:
x := 5
x += 5      -- equivale a (x = x + 5)
-- valor final de x = 10

➖ Azúcar Sintáctico: -=
Expresión corta equivalente a x = x - e.

Sintaxis:
comm ::= var '-=’ intexp ';'

Ejemplo:
x := 100
x -= 50     -- equivale a (x = x - 50)
-- valor final de x = 50

🏗️ Sintaxis Concreta
<intexp> ::= <boolexp> '?' <intexp> ':' <intexp>
<comm>   ::= <var> '+=’ <intexp> ';'
<comm>   ::= <var> '-=’ <intexp> ';'

🧱 Sintaxis Abstracta
data IntExp 
  = ...
  | Question BoolExp IntExp IntExp
