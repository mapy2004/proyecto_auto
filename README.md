# proyecto_auto
diablo coño cebolla
//
De momento lo único que he hecho ha sido crear 
un par de entidades mediante asignación y crear
la cadena de procesado teniendo en cuenta las
dos entidades distintas, de momento todo funciona
bien. :)

Fábrica de ensamblado de ordenadores donde se disponen de dos tipos, ordenadores de oficina y ordenadores gaming.

Inicialmente, se hace acopio de los elemenetos necesarios en el proceso de kitting (TRIA(5,8,15)), posteriormente se transportan a través de un transporter se lleva al ciclo de la cinta transportadora:

La cinta pasa por :
  - Preparación de la placa madre (oficina: TRIA(2,4,6) y gaming:TRIA(5,8,12))
  - Ensamblaje de la caja del ordenador (oficina: TRIA(10,15,25) y gaming:TRIA(15,20,30))
  - Intalar la gráfica (TRIA(2,3,5))
  - Estación de pruebas (TRIA(5,10,15))
  - Empaquetado (TRIA(3,5,7))

Sin embargo la secuancia de los ordenadores de oficina no pasan por el instalador de la gráfica.

Hay una serie de fallos en la preparación de la placa madre según una EXPO(1000) en minutos y cuando se da se descarta el elemento que esté siendo procesado y se espera a que se arregle que tarda 30 minutos. También se encuentran fallos en en ensamblaje, una EXPO(2000) en minutos en la que si se da un fallo se termina lo que se esté haciendo y esperará a arreglarse en 10 minutos antes de seguir.

