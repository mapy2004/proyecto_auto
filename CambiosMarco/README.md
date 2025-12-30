# proyecto_auto
diablo coño cebolla
//
De momento lo único que he hecho ha sido crear 
un par de entidades mediante asignación y crear
la cadena de procesado teniendo en cuenta las
dos entidades distintas, de momento todo funciona
bien. :)

Fábrica de ensamblado de ordenadores donde se disponen de dos tipos, ordenadores de oficina (70%) y ordenadores gaming (30%). Únicamenete se proporcionan nuevos materiales para la manufacturación durante las 8 primeras horas del día, es decir, el módulo create tiene un schedule para gestionarlo.

Inicialmente, se hace acopio de los elemenetos necesarios en el proceso de kitting (TRIA(5,8,15)), posteriormente se transportan a través de un transporter se lleva al ciclo de la cinta transportadora:

La cinta pasa por :
  - Preparación de la placa madre (oficina: TRIA(2,4,6) y gaming:TRIA(5,8,12))
  - Ensamblaje de la caja del ordenador (oficina: TRIA(10,15,25) y gaming:TRIA(15,20,30))
  - Intalar la gráfica (TRIA(2,3,5))
  - Estación de pruebas (TRIA(5,10,15))
  - Empaquetado (TRIA(3,5,7))
  - Descarga (TRIA(0.5,1,5))

Hay un proceso que únicamente es accesible mediante transporter y se llama Arreglo(oficina: TRIA(20,40,50) y gaming:TRIA(30,55,70))

Sin embargo la secuencia de los ordenadores de oficina no pasan por el instalador de la gráfica. En caso de fallo detectado en el proceso de la estación de pruebas (25% de fallo), se pide el transporter correspondiente y se pasa a Arreglo, cuando termine irá también en transporter a la salida directamente.

En la salida, los ordenadores puede ser que sean para particulares (80%) o para empresas (20%), en caso de ser para particulares saldrán directamente, en caso contrario se esperará a que lleguen 5 ordenadores de oficina o gaming (no se mezclan, o paquetes de oficina completos o de gaming) para sacarlos como un paquete completo (nueva entidad llamada Entidad_paquete).

Hay una serie de fallos en la preparación de la placa madre según una EXPO(15) en elementos procesados y cuando se da se descarta el elemento que esté siendo procesado y se espera a que se arregle que tarda 30 minutos. También se encuentran fallos en en ensamblaje, una EXPO(30) en elementos procesados en la que si se da un fallo se termina lo que se esté haciendo y esperará a arreglarse en 10 minutos antes de seguir.

En cuanto al tiempo de trabajo, todos los procesos están activos durante las 8 primeras horas del día, sin embargo, el proceso de ensamblado, el de instalar la gráfica y el de empaquetado al estar automatizados, también trabajan las últimas 8 horas del día para aligerar las colas para los nuevos productos del día. En pocas palabaras, hay dos schedules de recursos, uno diurno y otro asociado a la maquinaria.