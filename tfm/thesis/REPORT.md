# Descripción del proyecto

Detectar un tipo de función en un repositorio de código fuente implica identificar y localizar funciones específicas dentro del código. Esto puede ser útil en varias situaciones, como la detección de funciones criptográficas mencionada en tu documento.

La detección de funciones puede implicar el uso de técnicas de análisis estático de código, que examinan el código sin ejecutarlo, o de análisis dinámico, que observan el comportamiento del código mientras se ejecuta. También puede implicar el uso de técnicas de aprendizaje automático para identificar patrones en el código que sugieran la presencia de una función específica.

En el caso de las funciones criptográficas, por ejemplo, podrías estar buscando 
patrones que indiquen el uso de algoritmos de cifrado específicos, como AES o RSA. 
Esto podría implicar la búsqueda de nombres de funciones específicas, la presencia 
de ciertas constantes utilizadas en los algoritmos, o incluso patrones en la forma 
en que se manipulan los datos que sugieran un proceso de cifrado o descifrado.

Es importante tener en cuenta que la detección de funciones en el código fuente 
puede ser un desafío debido a factores como la obfuscación del código, las 
diferencias en la forma en que diferentes programadores pueden implementar la misma 
función, y la necesidad de evitar falsos positivos y falsos negativos.

# Antecedentes y estado actual del problema

La detección de funciones criptográficas en códigos fuente es un desafío importante 
en el campo de la seguridad informática. Actualmente, existen diversas técnicas y 
enfoques para abordar este problema, como el análisis estático y dinámico de código, 
pero aún hay margen de mejora en términos de precisión y eficiencia.

## Herramientas SAST

Las herramientas de Pruebas de Seguridad de Aplicaciones Estáticas (SAST, por sus siglas en inglés) están diseñadas para analizar el código fuente, el código de bytes o el código binario en busca de vulnerabilidades de seguridad sin ejecutar la aplicación. Estas herramientas identifican posibles problemas de seguridad mediante el análisis de la estructura del código, las dependencias y el flujo de datos. Aquí tienes una descripción de las herramientas SAST:

- Funcionalidad:

    * Las herramientas SAST escanean bases de código para identificar vulnerabilidades de seguridad, incluidas, entre otras, fallos de inyección, scripting entre sitios (XSS), configuraciones inseguras, debilidades criptográficas, y más.
    * Analizan el código en reposo, lo que significa que no necesitan ejecutar la aplicación, lo que las hace adecuadas para identificar vulnerabilidades temprano en el proceso de desarrollo.

- Lenguajes y Plataformas Soportadas:

    * Las herramientas SAST soportan varios lenguajes de programación, incluidos los populares como Java, C/C++, C#, 
    JavaScript, Python, Ruby, entre otros.
    * Algunas herramientas pueden ofrecer un soporte de lenguaje más amplio que otras, y algunas pueden 
    especializarse en lenguajes o marcos específicos.

- Técnicas de Análisis:

    * Las herramientas SAST utilizan una variedad de técnicas de análisis, incluida la coincidencia de patrones, el 
    análisis de flujo de datos, el análisis de flujo de control, el análisis de contaminación, y la traversía de árbol de sintaxis abstracta (AST).
    
    * Estas técnicas ayudan a identificar vulnerabilidades de seguridad, prácticas de codificación inseguras y 
    posibles puertas traseras dentro de la base de código.

- Personalización y Conjuntos de Reglas:

    * Muchas herramientas SAST permiten la personalización de conjuntos de reglas, lo que permite a los usuarios adaptar el análisis a sus requisitos específicos.
    * Los usuarios pueden habilitar o deshabilitar ciertas comprobaciones, ajustar los niveles de gravedad y crear reglas personalizadas para abordar políticas de seguridad específicas de la organización o requisitos de cumplimiento.


- Integración con el Ciclo de Vida del Desarrollo:

    * Las herramientas SAST pueden integrarse con varias herramientas y entornos de desarrollo, como entornos de desarrollo integrados (IDE), sistemas de control de versiones, tuberías de integración continua/entrega continua (CI/CD), y sistemas de seguimiento de problemas.
    * La integración permite a los desarrolladores recibir comentarios sobre problemas de seguridad directamente dentro de su flujo de trabajo de desarrollo, promoviendo la detección y corrección temprana de vulnerabilidades.


- Informes y Orientación para la Corrección:

    * Las herramientas SAST generan informes detallados que resaltan las vulnerabilidades de seguridad identificadas, 
    incluidas descripciones, ubicaciones dentro de la base de código, niveles de gravedad y orientación para la 
    corrección.
    * Los informes suelen incluir recomendaciones prácticas para ayudar a los desarrolladores a solucionar las 
    vulnerabilidades de manera eficiente.


- Escalabilidad y Rendimiento:

    * Las herramientas SAST varían en escalabilidad y rendimiento. Algunas herramientas pueden ser más adecuadas para bases de código pequeñas o medianas, mientras que otras pueden manejar proyectos grandes y complejos.
    * Las consideraciones de rendimiento incluyen la velocidad de análisis, el consumo de recursos y el soporte para procesamiento en paralelo.


- Mejora Continua:

    * Las herramientas SAST evolucionan con el tiempo para mantenerse al día con las amenazas de seguridad emergentes, lenguajes de programación, marcos y mejores prácticas.
    * Los proveedores actualizan regularmente sus herramientas con nuevas comprobaciones de seguridad, técnicas de análisis mejoradas y mejoras en la usabilidad y capacidades de integración.

# Objetivos del proyecto

Los objetivos de este proyecto son los siguientes:
- Implementar dos algoritmos para detectar funciones criptográficas en códigos fuente.
- Evaluar la efectividad y precisión de los algoritmos desarrollados.
- Investigar y analizar el estado del arte en la similitud de texto y en la similitud de código.
- Explorar los principios del aprendizaje automático, incluyendo modelos de aprendizaje profundo y aprendizaje superficial.
- Utilizar técnicas de Prompt Engineering y modelos de lenguaje de aprendizaje para mejorar la detección de funciones criptográficas.
- Entrenar modelos de WordEmbeddings y calcular la similitud entre vectores resultantes para determinar la similitud de funciones criptográficas.

# Requisitos de alto nivel

Los requisitos de alto nivel para este proyecto son los siguientes:
- Implementar algoritmos de detección de funciones criptográficas utilizando Prompt Engineering y modelos de lenguaje de aprendizaje.
- Desarrollar un enfoque basado en la partición del código en sentencias y el cálculo de similitud de vectores resultantes.
- Investigar y analizar el estado del arte en la similitud de texto y en la similitud de código.
- Evaluar la efectividad y precisión de los algoritmos implementados.
- Documentar los resultados y conclusiones obtenidas.

# Plan de trabajo

El plan de trabajo para este proyecto se divide en las siguientes etapas:
1. Investigación y revisión bibliográfica sobre detección de funciones criptográficas y similitud de texto y código.
2. Diseño e implementación del algoritmo basado en Prompt Engineering y modelos de lenguaje de aprendizaje.
3. Diseño e implementación del algoritmo basado en la partición del código y el cálculo de similitud de vectores.
4. Evaluación y comparación de los algoritmos desarrollados.
5. Documentación de los resultados obtenidos y redacción del informe final.

