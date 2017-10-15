#Se incluyen los ejemplos con los que se hace claridad hacerca de el funcionamiento de las nuevas caracteristicas adicionadas al interpretador, dichas nuevas caracteristicas corresponden a las especificaciones solicitadas de el taller 2


#Ejemplos de procedimientos con multiples argumentos 
let
x = proc (x y z ) +(+(x,y), z)
y = 12
in
let
x = proc (x) x
in
(x 1)
Resultado: 1

let
x = proc (x y z ) +(+(x,y), z)
y = 12
in
let
x = proc (x) x
in
(x 1 2 3)
Resultado: 6

let 
f = proc (x y) +(x,y) 
in 
let f = proc (x) x 
in (f 4 5)


#Ejemplos de aridad


let x = proc(x y) w in arity(x)

let x = proc (x y z a b c d) x in arity (x)

let x = 1 y = 0 in arity(x)

#Ejemplos de checkeo de definicion de variables

let x = proc(x y) x in defined-var?(x)
Resultado: 1

let x = proc(x y) x in defined-var?(r)
Resultado: 0

let r = 5 x = proc(x y) x in defined-var?(r)
Resultado: 1

let x = 5 in defined-var?(x)
Resultado: 1

let x = +(0,0) in defined-var?(x)
Resultado: 1

#Ejemplos de checkeo de procedimiento como valor 


checkeoProcedimientoComoValor(+(x,y))
Resultado: 0

checkeoProcedimientoComoValor(proc (a b) +(a,b))
Resultado: 1

let x = proc (x y z a b c d) x in checkeoProcedimientoComoValor (x)
Resultado: 1

let x = +(5,3) in checkeoProcedimientoComoValor (x)
Resultado: 0
