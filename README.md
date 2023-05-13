# Grid-CSS-basicos
Guia de CSS grid
grid-template-columns -> para indicar cuantas columnas quieres

grid -> shorthand de grid-template-columns y grid-template-rows separados por '/', primero los rows, despues las columns

gap -> indica la separacion entre items, es tambien un shorthand de column-gap y row-gap.

column-gap -> me indica la ubicacion y el tamaño que abarca un item en columnas concretamente

            column-gap: 1/3
            esta declaracion me dice que su ubicacion empezara desde la columna 1, y se extendera hasta la 3

row-gap -> me indica la ubicacion y el tamaño que abarca un item en columnas concretamente

            row-gap: 2 / 4
            esta declaracion me dice que su ubicacion empieza en la fila 2 y se extiende hasta la fila 4

grid-auto-flow -> me indica cómo funciona el algoritmo de colocación automática, especificando exactamente cómo los elementos colocados automáticamente fluyen hacia la cuadrícula.

  valores:
        row
        Los artículos se colocan llenando cada fila a su vez, agregando nuevas filas según sea necesario. Si no se proporciona rowni , se asume.columnrow

        column
        Los artículos se colocan llenando cada columna a su vez, agregando nuevas columnas según sea necesario.

        dense
        El algoritmo de empaquetamiento "denso" intenta llenar los agujeros antes en la cuadrícula, si aparecen elementos más pequeños más tarde. Esto puede hacer que los artículos parezcan desordenados, cuando al hacerlo se llenarían los huecos que dejan los artículos más grandes.


grid-template-areas: "izquierda centro derecha"; -> me permite definir y nombrar mis areas dentro de grid. Es como dibujar el contenido, es muy util cuando los layouts son mas complejos. ya que no son necesarios los grid-(column/row). esto lo que hace es que le da un nombre a las areas que definimos con grid-templete-(columns/rows).

        grid-templete-columns: 1fr 3fr 1fr
        grid-templete-areas: "izq  centro derecha"
    
    1fr -> izq
    3fr -> centro
    1fr -> derecha

tambien podemos definir areas en filas, en ves de poner los nombres en una sola comilla podemos ponerlos con diferentes comilas. indicando asi que se tratan de fila y no de columnas una alado de otra.

    grid-template-areas: "izquierda"
                          "centro"
                          "derecha";

unidos: 
        grid-template-areas:"header header header"
                            "nav nav nav"
                            "main main sidebar"
                            "footer footer footer";

grid-area -> especifica el tamaño y la ubicación de un elemento, podemos darle la ubicacion de un area en concreto que ya hallamos definido en grid-templete-areas.

    grid-area: "izq";

grid template -> shorthand de grid-template-areas, grid-template-column y grid-template-rows, ejemplo:

    grid-template:  "header header header" 2fr "nav nav nav" 1fr  "main main sidebar" 6fr "footer footer footer"; 2fr / 1fr 1fr 1fr
    
    Aqui estamos diciendo que queremos que queremos nombrar esas areas, con un tamaño de row (fila) del numero especificado a la derecha de cada area, y despues del '/' especificamos las columnas 

align-items, align-content, place-content -> me permite alinear el contenido verticalmente.


auto-fill -> repite el patrón de columnas o filas tantas veces como sea posible, llenando todo el espacio disponible en el contenedor, incluso si quedan celdas vacías. Por ejemplo:

    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));

auto-fit -> funciona de manera similar a auto-fill, pero en lugar de agregar celdas vacías, ajusta el ancho de las columnas o filas existentes para llenar todo el espacio disponible en el contenedor. Por ejemplo:

    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
