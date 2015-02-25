# Plantilla para apunte
Plantilla utilizada en la mayoría de los apuntes del proyecto FIUBA Apuntes.

El directorio `paquetes-apunte` posee paquetes personalizados para incluir 
información común a todos los apuntes del proyecto.

Si se va a iniciar un nuevo apunte, lo recomendado es copiar el mencionado 
directorio y el archivo `apunte.tex` (puede renombrar este último archivo si 
se desea).

En caso de que deba incluir los paquetes en un proyecto existente, 
lo recomendable es copiar el directorio `paquetes-apunte`. Debe agregar en 
el archivo `.tex` donde desea utilizarlo como ruta de gráficos el directorio 
copiado, insertando el siguiente código antes de comenzar el documento:
```tex
\graphicspath{ {./paquetes-apunte/} }
```

En caso de que ya tenga definido parámetros de ```graphicpath```, debe 
incluir la ruta del directorio de paquetes.

Como suele ocurrir que la ruta del directorio de paquetes se incluya en 
diversos lugares, es una buena práctica definir una variable (comando en Latex) 
que almacene la ruta de la siguiente forma:
```tex
\newcommand{\rutapaquetes}{./paquetes-apunte}
```

Con esta nueva variable, la inclusión del directorio de gráficos resulta:
```tex
\graphicspath{ {\rutapaquetes/} }
```

## Plantilla
`apunte` [`.tex`](apunte.tex?raw=true) [`.pdf`](apunte.pdf?raw=true)

## Paquete `caratula`
Paquete para generar la carátula de los apuntes.

### Uso
El paquete se debe incluir de la siguiente manera:
```tex
\usepackage[mostrarlicencia]{\rutapaquetes/caratula}
```
Las opciones disponibles que posee son:
* `mostrarlicencia` la cual muestra la licencia en la carátula y la página con 
el detalle de la misma. Su inverso es `ocultarlicencia` que es el valor por 
defecto.

Los comandos que dispone este paquete son:
```tex
\materia{Materia} % Nombre de la materia (obligatorio)
\tipoapunte{Tipo de Apunte (Teórico o Práctico)} % Muestra el tipo de apunte
\tema{Tema de la Materia} % Muestra el tema que incluye el apunte
\subtema{Subtema} % Muestra el subtema que incluye el apunte
\maketitle % Genera la carátula (reemplaza al comando original)
```

### Ejemplo de carátula con licencia
![Ejemplo de carátula](ejemplo-caratula.png?raw=true "Ejemplo de carátula con licencia")

### Ejemplo de página de licencia
![Ejemplo de página de licencia](ejemplo-pagina-licencia.png?raw=true "Ejemplo de carátula")


### Agradecimientos
Este paquete está basado en la versión del paquete caratula v 0.5 para 
documentos del DC (FCEyN), hecha por Brian Cardiff y Nico Rosner. 
[Codigo Fuente Base](https://github.com/bcardiff/dc-tex)

## Extensión `acerca-del-proyecto`
Incluye una sección con información acerca del proyecto FIUBA Apuntes, detalla 
cómo colaborar y provee los enlaces necesarios para obtener más información.

Para agregar la información acerca del proyecto se debe incluir, en el 
lugar donde se desea colocar dicha sección, el siguiente comando:
```tex
\subfile{\rutapaquetes/acerca-del-proyecto.tex}
```

## Paquete `macros`
Paquete con macros útiles como comandos y entornos nuevos.
Por ahora solo se provee un solo comando para generar un entorno nuevo cuyo 
contenido se mostrará dentro de un cuadro con un título. Dicho cuadro es 
utilizado para distinguir las propiedades, corolarios y teoremas de los apuntes
de Análisis Matemático, Algebra y otros.

### Uso
El paquete se debe incluir de la siguiente manera:
```tex
\usepackage{\rutapaquetes/macros}
```
Los comandos que dispone este paquete son:
```tex
\cuado{teorema}{blue} % Crea el entorno teorema con el estilo de color azul para el cuadro

\begin{teorema*}
	Contenido a colocar dentro del del cuadro de teorema
\end{teorema*}
```
Nótese el caracter * en el entorno teorema. Sin dicho caracter el entorno 
funciona de la misma manera. Pero se espera que en un futuro (cercano quizás)
los entornos sin el * sean numerados con posibilidad de crear un índice del 
tipo de entorno creado (en el ejemplo, un índice de teoremas).

### Ejemplo de macro de cuadro
![Ejemplo de cuadro de teorema con color azul](ejemplo-cuadro-azul.png?raw=true "Ejemplo de cuadro de teorema con color azul")

## Paquete `colaboradores`
Incluye una sección donde se menciona a las personas que han colaboradores 
en la creación, corrección y mejora del apunte.

El paquete provee la opción de incluir revisores, es decir, personas que han 
revisado y han realizado una valoración del mismo, pudiendo solicitar 
correcciones o mejoras. Esta opción está pensada para incluir como mención 
especial a los docentes de la facultad que han colaborado con el apunte.

**Si va a incluir el nombre de una persona como colaborador o revisor, consulte 
a esa persona si está interesada en figurar en la lista de colaboradores.**

### Uso
El paquete se debe incluir de la siguiente manera:
```tex
\usepackage{\rutapaquetes/colaboradores}
```

Las opciones disponibles que posee son:
* `mostrarrevisores` muestra la lista de revisores cargados. Si no hay revisores cargados, la compilación del archivo latex fallará. Su inverso es `ocultarrevisores` que es el valor por defecto.

Los comandos que dispone este paquete son:
```tex
\colaborador{Colaborador 1} % Ingresa un colaborador (es necesario proveer 
                            % al menos uno)
\colaborador{Colaborador 2} % Ingresa otro colaborador
\revisor{Dr. Profesor}{10/01/2015} % Ingresa un revisor del apunte y la fecha 
                                   % de la última revisión realizada por el mismo
\makeseccioncolaboradores % Genera la sección de colaboradores
```

### Ejemplo de sección colaboradores
![Ejemplo de sección colaboradores](ejemplo-seccion-colaboradores.png?raw=true "Ejemplo de sección colaboradores")

## Paquete `historial`
Incluye una sección que muestra un resumen cronológico de los cambios más 
importantes realizados en el apunte.

### Uso
El paquete se debe incluir de la siguiente manera:
```tex
\usepackage{\rutapaquetes/historial}
```
Los comandos que dispone este paquete son:
```tex
\revision{28/12/2014}{Versión inicial.} % Agrega una revisión
\revision{10/01/2015}{Múltiples correcciones.} % Agrega una revisión
\makehistorial % Genera la sección de historial
```

### Ejemplo de sección historial
![Ejemplo de sección historial](ejemplo-seccion-historial.png?raw=true "Ejemplo de sección historial")
