# Tarea UT5 - XQuery
## ¿Qué es XQuery y para qué se utiliza?
XQuery es un lenguaje utilizado para buscar y extrar elementos o atributos de documentos XML.

## ¿Cómo se crea una consulta con XQuery?
Las consultas XQuery utilizan funciones, por ejemplo la función **_doc('file.xml')_** con la que abrimos el documento XML.

Una vez abierto el documento debemos especificar la ruta que queremos consultar:
**_doc('file.xml')/etiqueta/etiqueta/etiqueta_**

También podemos utilizar predicados para concretar más el resultado que queremos:
**_doc('file.xml')/etiqueta/etiqueta/etiqueta[@atributo]_**

En el último ejemplo estaríamos seleccionando aquellas etiquetas que tengan ese atributo.

## ¿Cuáles son las expresiones FLWOR de XQuery?
**FLWOR** son las siglas de: 
* **For:** Selecciona los elementos especificados en la ruta.
* **Let:** Asigna el resultado a una variable.  
* **Where:** Filtra los resultados con un predicado.
* **Order by:** Ordena los resultados.
* **Return:** Devuelve el resultado final.

## ¿Cómo podemos utilizar XQuery con HTML?
Dentro de la sintaxis HTML podemos hacer consultas con las expresiones FLWOR de XQuery para mostrar los resultados en nuestra página.

Por ejemplo si tenemos un XML con nuestros contactos y queremos mostrarlos en una lista HTML lo podríamos hacer de la siguiente manera:

```
<html>
    <head></head>
    <body>
        <ul>
        {
            for $x in doc("agenda.xml")/agenda/contactos/identificadores/nombre
            order by $x
            return <li>{$x}</li>
        }
        </ul>
    </body>
</html>
```