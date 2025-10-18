Después de compilar su circuito, necesita realizar una configuración de confianza para generar claves de prueba y verificación.

## Comprender la configuración de confianza

 - **Configuración de confianza:** Un proceso requerido para que zk-SNARKs genere los parámetros necesarios para la generación y verificación de pruebas.
 - Puedes elegir entre diferentes protocolos como **Groth16** y **Plonk**.

## Realizar la configuración de confianza

1. En la sección **Configuración y exportaciones**, seleccione el **Esquema de prueba**:
    - Elija entre **Groth16** o **Plonk**. Usaremos **Groth16** para este tutorial.

2. Elija el archivo **Power of Tau** apropiado del menú desplegable. Este archivo es necesario para la configuración de confianza.
    - Si no está seguro, seleccione la opción predeterminada.

3. Haga clic en el botón **Configuración** para iniciar el proceso de configuración de confianza.

4. Puede habilitar **Exportar clave de verificación** para obtener los parámetros de verificación.

5. Puede habilitar **Contrato de verificación de exportación** si tiene la intención de verificar las pruebas en cadena.

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-5/images/trusted_setup.png" alt="trusted-setup" width=330 height=350>

**Nota:** La configuración de confianza puede llevar algún tiempo, dependiendo de la complejidad de su circuito.

En el siguiente paso, calcularemos el testigo de nuestro circuito.
