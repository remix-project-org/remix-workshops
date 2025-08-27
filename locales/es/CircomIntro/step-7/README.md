Con el testigo calculado, el paso final es generar una prueba que pueda ser verificada por otros.

## Generar la prueba

1. En la sección **Generar prueba**, tiene la opción de **Exportar datos de llamada del verificador**.
    - Active la casilla de verificación **Exportar datos de llamada del verificador** si planea verificar la prueba en cadena.
2. Haga clic en el botón **Generar prueba**.

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-7/images/generate_proof.png" alt="generate-proof" width=280 height=120>

## Entendiendo el resultado

 - Después de generar la prueba, el complemento mostrará los datos de la prueba.
 - Si habilitó **Exportar datos de llamada del verificador**, también proporcionará los datos de llamada necesarios para la verificación en cadena.

<img src="https://raw.githubusercontent.com/ethereum/remix-workshops/master/CircomIntro/step-7/images/proof_generated.png" alt="proof-generated" width=310 height=350>

## Próximos pasos

 - **Verificación:** Puede usar la clave de verificación o el contrato exportado anteriormente para verificar la prueba.
 - **Verificación en cadena:** Si está familiarizado con los contratos inteligentes, puede implementar el contrato de verificación y utilizar los datos de llamada para realizar la verificación en cadena.

\*\*¡Felicidades! \*\* Has escrito con éxito un circuito Circom, lo has compilado, realizado una configuración confiable, calculado un testigo y generado una prueba usando Remix-IDE.

## Recursos adicionales

 - [Documentación de Circom](https://docs.circom.io/)
 - [Documentación de Remix-IDE](https://remix-ide.readthedocs.io/)
 - [Explicación de las pruebas de conocimiento cero](https://zkproof.org/)

Siéntase libre de experimentar con circuitos más complejos y explorar aún más las capacidades de Circom y Remix-IDE.
