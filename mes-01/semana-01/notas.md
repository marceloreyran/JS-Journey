** Como regla general, solo los scripts más simples se colocan en el HTML. Los más complejos residen en archivos separados.

La ventaja de un archivo separado es que el navegador lo descargará y lo almacenará en caché.

Otras páginas que hacen referencia al mismo script lo tomarán del caché en lugar de descargarlo, por lo que el archivo solo se descarga una vez.

Eso reduce el tráfico y hace que las páginas sean más rápidas.

<details>

Podemos usar una etiqueta <script> para agregar código JavaScript a una página.
Los atributos type y language no son necesarios.
Un script en un archivo externo se puede insertar con  <script src="path/to/script.js"> </script>.
Hay mucho más que aprender sobre los scripts del navegador y su interacción con la página web. Pero tengamos en cuenta que esta parte del tutorial está dedicada al lenguaje JavaScript, por lo que no debemos distraernos con implementaciones específicas del navegador. Usaremos el navegador como una forma de ejecutar JavaScript, lo cual es muy conveniente para la lectura en línea, pero es solo una de muchas.



</details>