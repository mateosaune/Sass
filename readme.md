# SASS
---
## CSS PLANO (DESVENTAJAS)
- **Repetición de código**: Sin reutilización eficiente.
- **Modularidad limitada**: Difícil de mantener con archivos grandes.

```css
.container {
  color: red;
}
.container header {
  color: red;
}
.container footer {
  color: blue;
}
```
---
## QUE ES UN PROCESADOR

- Un procesador convierte código SASS u otro lenguaje extendido en CSS tradicional.

---

## VENTAJAS
Características avanzadas para facilitar la escritura y mantenimiento del código:

- **Variables**: Reutilización de valores constantes como colores y tamaños.
- **Anidamiento**: Organización jerárquica de selectores, lo que hace el código más limpio.
- **Ampersand (&)**: Uso para referirse al selector padre en reglas anidadas.
- **Modularidad**: Posibilidad de dividir el código en archivos parciales reutilizables.

---

## VARIABLES
Facilita la modificación global de estilos sin necesidad de buscar y reemplazar valores en variables.

```scss
$primaryColor: black;

p{
    $primaryColor: blue;
    color: $primaryColor;
}
```
---

## ANIDAMIENTO (SELECTORES)

En SASS, puedes anidar selectores dentro de otros, lo que refleja mejor la estructura del HTML y facilita la lectura del código. Esto es útil para aplicar estilos de manera más clara a elementos anidados.
```scss
.container {
    color: red;
    
     header{
        color:red;
    }
     footer{
        color:blue;
    }
}
```

## ANIDAMIENTO AMPERSAND(&)

El símbolo **&** en SASS permite referirse al selector padre dentro de reglas anidadas. 

```scss
.container {
    color: red;
    
    & header{
        color:red;
    }
    & footer{
        color:blue;
    }
}
```

## IMPORTACION (MODULARIDAD)(PARTIAL)

Conocidos como **partials**, files que normalmente comienzan con un guion bajo (`_`), pueden ser importados en un archivo principal utilizando la directiva `@import`. Esta práctica mejora la modularidad, la organización y el mantenimiento del código.

```scss
// _variables.scss
*,*::after,*::before{
    box-sizing: border-box;
    padding: 0;
    margin: 0;
}
// _header.scss
.header{
    display: block;

    p {
        color: red;
    }
}
// _menu.scss
.menu{
    color:red;
}
// _footer.scss
.footer{
    background-color: red;
}
// styles.scss
@import 'variables';
@import 'header';
@import 'menu';
@import 'footer';

body {
    background-color: #252525;
    color: whitesmoke;
    font-family: Arial, Helvetica, sans-serif;
    margin: 20px;
}