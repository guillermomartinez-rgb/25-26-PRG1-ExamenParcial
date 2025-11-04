
## Pregunta 1

Archivo: `Edificio.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/bca521c60726a8fabc73ebc9281552231873d9fb/entregas/elhadjiNiang/src/reto003/Edificio.java) (Reto 003)

```java
System.out.println("Dia " + dia + " - " + hora + ":00h ");
```

¿Qué observas en este código?
Las variables dia y hora no están definidas en el fragmento de código mostrado. Si no se han declarado previamente, el programa generará un error de compilación
---

## Pregunta 2

Archivo: `DibujadorDeEdificio.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/4fb82157b5760bf9f83ccadef799ba24adf4cdc2/entregas/sanmiguelHector/reto-003/DibujadorDeEdificio.java) (Reto 003)

```java
final String VENTANA_CERRADA = ":[ ]:";
final String VENTANA_ABIERTA_LUZ_APAGADA = ":[º]:";
final String VENTANA_ABIERTA_LUZ_ENCENDIDA = ":[*]:";
```

¿Qué observas en este código?
En Java, las constantes suelen declararse como public static final, especialmente si se van a usar en varias partes del programa.
Ejemplo: public static final String VENTANA_CERRADA = ":[ ]:";

---

## Pregunta 3

Archivo: `UnEdificio.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/1ce0c911d2fddb8930e1a76dea5c498a875b9fe8/entregas/marcos.huidobro/UnEdificio.java) (Reto 003)

```java
if (i < lado - 1) fila += ":";
```

¿Qué observas en este código?
Obserbo dos problemas: 
1: Uso de concatenación dentro de bucles: Cada vez que se usa fila += ... en un bucle, se crea una nueva cadena (porque los String en Java son inmutables).
En casos de muchas iteraciones, puede afectar el rendimiento.
2:Legibilidad del código: Si se omiten las llaves { }, puede causar confusión si se agrega otra instrucción después del if.
---

## Pregunta 4

Archivo: `edificio.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/fc37f36790acb17b30da59944d74627149443ed5/entregas/raposoEdgar/edificio.java) (Reto 003)

```java
while (dia <= DIAS) {
    int consumoDia = 0;
    // ...
    int hora = 0;
    while (hora < HORAS) {
        // ...
        hora++;
    }
}
```

¿Qué observas en este código?
En este caso tambien obserbo dos probemas:
1:Incremento de la variable dia: En el fragmento mostrado no aparece dia++.
Si no se incrementa dia dentro del bucle, el programa quedará en un bucle infinito.
La solucion a este problema seria: 
while (dia <= DIAS) {
    int consumoDia = 0;
    int hora = 0;
    while (hora < HORAS) {
        // ...
        hora++;
    }
    dia++; // 
}
2:Reinicialización de variables: Es correcto que hora se reinicie a 0 en cada día, pero hay que asegurarse de no declarar dia dentro del bucle.
---

## Pregunta 5

Archivo: `EdificioEnLaSemana.java` — [Ver archivo](https://github.com/mmasias/25-26-PRG1/blob/ec637ba447a91c88c6b9ef4161a464cbc2d26250/entregas/melgaresjose/src/retoBase/EdificioEnLaSemana.java) (Reto 003)

```java
System.out.print(habitacion == 3 ? COLUMNA_CENTRAL: "");
```

¿Qué observas en este código?
En este caso sigo obserbando dos problemas:
1:Dependencia de variables externas: Habria que asegurarse de que la variable habitacion y la constante COLUMNA_CENTRAL estén declaradas e inicializadas antes de usar esta línea, o el código no compilará.
2:Salida sin salto de línea: System.out.print() no agrega salto de línea al final. Si se desea que el resultado aparezca en una nueva línea, se debe usar System.out.println().