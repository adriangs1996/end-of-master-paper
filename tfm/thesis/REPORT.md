# Descripción del proyecto

Detectar un tipo de función en un repositorio de código fuente implica identificar y localizar funciones específicas dentro del código. Esto puede ser útil en varias situaciones, como la detección de funciones criptográficas, creando
un inventario de los recursos criptográficos presentes en el software base y que en un futuro
pudieran estar expuestos a actualizaciones o modificaciones.

El inventariado criptográfico es de suma importancia en empresas con grandes preocupaciones por su
seguridad en las redes y comunicaciones, ya que en un futuro no muy lejano, la computación cuántica
cambiará el panorama de la criptografía; y cambios estructurales en código base sería prácticamente
imposible de no conocer los recursos criptográficos existentes y cuáles de ellos se ve afectado.

La detección de funciones puede implicar el uso de técnicas de análisis estático de código, que examinan el código sin 
ejecutarlo, o de análisis dinámico, que observan el comportamiento del código mientras se ejecuta. También puede 
implicar el uso de técnicas de aprendizaje automático para identificar patrones en el código que sugieran la presencia 
de una función específica.

En el caso de las funciones criptográficas, por ejemplo, podríamos buscar 
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

### Herramientas SAST

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

    * Muchas herramientas SAST permiten la personalización de conjuntos de reglas, lo que permite a los usuarios adaptar 
    el análisis a sus requisitos específicos.
    * Los usuarios pueden habilitar o deshabilitar ciertas comprobaciones, ajustar los niveles de gravedad y crear 
    reglas personalizadas para abordar políticas de seguridad específicas de la organización o requisitos de 
    cumplimiento.


- Integración con el Ciclo de Vida del Desarrollo:

    * Las herramientas SAST pueden integrarse con varias herramientas y entornos de desarrollo, como entornos de 
    desarrollo integrados (IDE), sistemas de control de versiones, tuberías de integración continua/entrega continua (CI/
    CD), y sistemas de seguimiento de problemas.
    * La integración permite a los desarrolladores recibir comentarios sobre problemas de seguridad directamente dentro 
    de su flujo de trabajo de desarrollo, promoviendo la detección y corrección temprana de vulnerabilidades.


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

    * Las herramientas SAST evolucionan con el tiempo para mantenerse al día con las amenazas de seguridad emergentes, 
    lenguajes de programación, marcos y mejores prácticas.
    * Los proveedores actualizan regularmente sus herramientas con nuevas comprobaciones de seguridad, técnicas de 
    análisis mejoradas y mejoras en la usabilidad y capacidades de integración.

Herramientas como SonarCube, o Snyk, tienen una suite SAST que son capaces de detectar patrones anómalos en
el código fuente, sobre todo a la hora de analizar entradas sin sanitizar, lo que los convierte en herramientas
invaluables para escanera vulnerabilidades de tipo SQLInjection, XSS, Remote Code Execution, etc. Otra 
carácterística de estos sistemas, es que analizan los requerimientos de software de terceros (públicos)
detectando versiones que puedan contener vulnerabilidades, usualmente apoyándose en bases de datos de CVE, y
por ejemplo, se pueden detectar vulnerabilidades en algoritmos criptográficos que se basen en bibliotecas, por ejemplo,
si usamos una versión de pycryptodome antigua, en Python, probablemente detecta que se usa un MD5 o un SHA512 vulnerable
a ciertos tipos de ataques.

Sin embargo, estas herramientas no son capaces de detectar si se implementa un tipo de Algoritmo de modo
privado, por ejemplo, si lanzamos la herramienta sobre el repositorio de OpenSSL, probablemente no detecte
las distintas implementaciones de RSA o SHA que hay presente en el repo.

# Objetivos del proyecto

En este proyecto nos proponemos crear una herramienta que sea capaz de detectar y clasificar
el uso de algoritmos de cifrado (tanto de terceros como código propietario) en un repositorio
perteneciente a alguna organización. Para ello, implementaremos 2 algoritmos, basados en dos
modelos distintos de aprendizaje automático, que nos permitirán detectar si una función en un
código propietario es de cifrado o descifrado, y, de serlo, intentaremos clasificarlo como RSA, SHA,
CHACHA20, MD5, Curvas Elípticas, Simple XOR, Bcrypt, ect.
Acompañado a esto, integraremos alguna herramienta open source de análisis estático de dependencias,
de modo que podamos realizar el inventariado de bibliotecas que se usen en el código base.

Dicho esto, los objetivos son los siguientes:
- Recopilar muestras de código que implementen algoritmos criptográficos en varios lenguajes y clasificarlos.
- Implementar dos algoritmos para detectar funciones criptográficas en códigos fuente.
- Evaluar la efectividad y precisión de los algoritmos desarrollados.
- Investigar y analizar el estado del arte en la similitud de texto y en la similitud de código.
- Explorar los principios del aprendizaje automático, incluyendo modelos de aprendizaje profundo y aprendizaje superficial.
- Utilizar técnicas de Prompt Engineering y modelos de lenguaje de aprendizaje para mejorar la detección de funciones criptográficas.
- Entrenar modelos de WordEmbeddings y calcular la similitud entre vectores resultantes para determinar la similitud de funciones criptográficas.
- Integrar herramientas SAST para la detección de Dependencias criptográficas

# Requisitos de alto nivel

Los requisitos de alto nivel para este proyecto son los siguientes:
- Conocimientos de ventajas y funcionamientos de la IA Generativa.
- Principios de la vectorización de palabras, oraciones, documentos y tesauros.
- Dominio de la estructura y funcionamiento de los algoritmos criptográficos.
- Prompt Engineering
- Fundamentos de redes neuronales y aprendizaje profundo y superficial
- Clustering y similitud de Texto


# Plan de trabajo

El plan de trabajo para este proyecto se divide en las siguientes etapas:
1. Investigación y revisión bibliográfica sobre Machine Learning, DNN, Word Embeddings y clustering.
2. Investigación y revisión bibliográfica sobre detección de funciones criptográficas y similitud de texto y código.
3. Investigación y revisión bibliográfica sobre estructura de distintos algoritmos criptográficos y si existe algún
tipo de indicador que ayude a diferenciar estas funciones de otras.
4. Recolección y clasificación de implementaciones de algoritmos criptográficos en distintos lenguajes.
5. Diseño e implementación del algoritmo basado en Prompt Engineering y modelos de lenguaje de aprendizaje utilizando
algún API pública.
6. Diseño e implementación del algoritmo basado en la partición del código y el cálculo de similitud de vectores 
(Word2Vec).
7. Evaluación y comparación de los algoritmos desarrollados.
8. Documentación de los resultados obtenidos y redacción del informe final.

