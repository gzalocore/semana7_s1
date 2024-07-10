# INTRODUCCION SASS

    - SASS(Syntactically Awesome Stylesheets) es un preprocesador CSS que extiende las capacidades de CSS con características adicionales que facilitan la creación de hojas de estilo más complejas y mantenibles.

# PREPROCESADOR
    - Un preprocesador en SASS es una herramienta que permite escribir CSS de manera más eficiente y con características adicionales que no están disponibles en CSS puro. SASS es uno de los preprocesadores CSS más populares y proporciona una serie de características avanzadas que facilitan la escritura y el mantenimiento de hojas de estilo.

# DESVENTAJAS CSS PLANO

    1. Repetición de Código: En CSS plano, es común repetir las mismas reglas y propiedades múltiples veces, lo que puede llevar a un código inflado y difícil de mantener.
    2. Falta de Variables: No hay soporte para variables, lo que significa que los valores comunes, como colores y tamaños, deben ser redefinidos en cada lugar que se usen. Esto dificulta la actualización de estos valores.
    3. Mala Escalabilidad: A medida que un proyecto crece, la hoja de estilos puede volverse inmanejable y difícil de escalar debido a la falta de modularidad y organización intrínseca en CSS plano.
    4. Selección Específica Compleja: La anidación de selectores no es posible, lo que puede llevar a selectores más largos y menos legibles cuando se trata de estructuras HTML anidadas.
    5. Falta de Funcionalidades Avanzadas: CSS plano carece de características avanzadas como mixins, funciones y herencia, que pueden hacer que la aplicación de estilos complejos y reutilizables sea más complicada.
    6. Mantenimiento Difícil: Realizar cambios globales puede ser tedioso y propenso a errores, ya que no hay una manera fácil de cambiar un valor en un solo lugar y que se actualice en toda la hoja de estilos.
    7. Problemas de Consistencia: Mantener la consistencia en el diseño puede ser desafiante sin las herramientas adecuadas para la reutilización y centralización de estilos.

# VENTAJAS DEL SASS

    1. VARIABLES: SASS permite definir variables, lo cual facilita la gestión de colores, fuentes y otros valores reutilizables en todo el proyecto. Esto reduce la repetición y facilita la actualización de estilos globales.

    ``` CSS
    $primary-color: #3498db;
    $font-stack: Helvetica, sans-serif;

    body {
    color: $primary-color;
    font-family: $font-stack;
    }
    ```

    2. SCOPE: se refiere a la visibilidad y accesibilidad de variables. El SCOPE(alcance) en SASS es similar al scope en otros lenguajes de programación, determinando dónde se pueden usar ciertos identificadores dentro del código CSS.

    ``` CSS
    $global-color: blue;

    body {
      background-color: $global-color; // Uso de una variable global

      // Definición de una variable local dentro de .container
      .container {
        $local-color: red;
        color: $local-color; // Uso de una variable local dentro del scope
      }
    }
    ```

    3. ANIDAMIENTO: El anidamiento de selectores en Sass mejora la legibilidad del código y refleja mejor la estructura HTML.

    ``` CSS
    nav {
        ul {
          margin: 0;
           padding: 0;
           list-style: none;
        }

          li { display: inline-block; }
         a {
            text-decoration: none;
            color: $primary-color;
        }
    }
    ```

    4. AMPERSAND PADRE: El ampersand (&) en SASS es un símbolo que representa el selector padre en el contexto actual. Se utiliza para referirse al selector en el que se encuentra anidado, permitiendo una escritura más eficiente y clara de los estilos anidados y las pseudo-clases.

    ``` CSS
    ul{
        color: red;
        & li{
            & a{
                text-decoration: none;
            }
            color: red;
        }
    }
    ```
    5. IMPORT: SASS permite dividir el CSS en múltiples archivos parciales y luego importarlos en un solo archivo principal. Esto mejora la organización y mantenibilidad del código.

    ``` CSS
    // _reset.scss
    body { margin: 0; padding: 0; }

    // styles.scss
    @import 'reset';
    @import 'variables';
    @import 'base';
    @import 'layout';
    @import 'components';

    ```