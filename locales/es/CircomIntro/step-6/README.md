Con la configuración de confianza completada, ahora puede calcular el testigo de su circuito basándose en entradas específicas.

## ¿Qué es un testigo?

 - Un **Testigo** es un conjunto de valores que satisfacen todas las restricciones de su circuito. Incluye todos los números intermedios y resultados que satisfacen las reglas del circuito. El testigo se utiliza en pruebas de conocimiento cero para demostrar que usted conoce una solución válida al problema sin mostrar realmente la solución en sí. Esto permite a otros verificar que hiciste todo correctamente mientras mantienes privados tus números y cálculos específicos.
 - Es esencial para generar una prueba.

## Entrada de valores

1. En la sección **Computar testigo**, verá campos de entrada generados dinámicamente en función de las entradas de su circuito.
2. Introduzca valores para `a` y `b`. Por ejemplo:
    - `a = 3`
    - `b = 4`

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-6/images/compute_witness.png" alt="compute-witness" width=280 height=240>

## Calculando el testigo

1. Después de ingresar las entradas, haga clic en el botón **Computar testigo**.
2. El complemento calculará el testigo en función de sus entradas.
3. Si tiene éxito, verá `multiplier.wtn` creado en el directorio `.bin` en el explorador de archivos.

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-6/images/witness_computed.png" alt="witness-computed" width=340 height=350>

**Nota:** Si hay algún error, asegúrese de que sus entradas sean válidas y satisfagan las restricciones del circuito.

En el siguiente paso, generaremos una prueba usando el testigo calculado.
