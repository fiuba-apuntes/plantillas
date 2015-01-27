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
\usepackage{\rutapaquetes/caratula}
```

Los comandos que dispone este paquete son:
```tex
\materia{Materia} % Nombre de la materia (obligatorio)
\tipoapunte{Tipo de Apunte (Teórico o Práctico)} % Muestra el tipo de apunte
\tema{Tema de la Materia} % Muestra el tema que incluye el apunte
\subtema{Subtema} % Muestra el subtema que incluye el apunte
\maketitle % Genera la carátula (reemplaza al comando original)
```

### Ejemplo
![Ejemplo de carátula](ejemplo-caratula-apunte.png?raw=true "Ejemplo de carátula")

### Agradecimientos
Este paquete está basado en la versión del paquete caratula v 0.5 para 
documentos del DC (FCEyN), hecha por Brian Cardiff y Nico Rosner. 
[Codigo Fuente Base](https://github.com/bcardiff/dc-tex)

## Extensión `sobre-el-proyecto`
Incluye una sección con información sobre el proyecto FIUBA Apuntes, detalla 
cómo colaborar y provee los enlaces necesarios para obtener más información.

Para agregar la información sobre el proyecto se debe incluir, en el 
lugar donde se desea colocar dicha sección, el siguiente comando:
```tex
\subfile{\rutapaquetes/sobre-el-proyecto.tex}
```

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

Los comandos que dispone este paquete son:
```tex
\colaborador{Colaborador 1} % Ingresa un colaborador (es necesario proveer 
                            % al menos uno)
\colaborador{Colaborador 2} % Ingresa otro colaborador
\revisor{Dr. Profesor}{10/01/2015} % Ingresa un revisor del apunte y la fecha 
                                   % de la última revisión realizada por el mismo
\makeseccioncolaboradores % Genera la sección de colaboradores
```

### Ejemplo
![Ejemplo de sección colaboradores](ejemplo-colaboradores-apunte.png?raw=true "Ejemplo de sección colaboradores")