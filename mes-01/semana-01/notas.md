***
 Como regla general, solo los scripts más simples se colocan en el HTML. Los más complejos residen en archivos separados.

La ventaja de un archivo separado es que el navegador lo descargará y lo almacenará en caché.

Otras páginas que hacen referencia al mismo script lo tomarán del caché en lugar de descargarlo, por lo que el archivo solo se descarga una vez.

Eso reduce el tráfico y hace que las páginas sean más rápidas.

<details>

  <summary>Haz clic para ver el resumen</summary>

  Podemos usar una etiqueta `<script>` para agregar código JavaScript a una página.
  
  * Los atributos `type` y `language` no son necesarios.
  * Un script externo se inserta con `<script src="path/to/script.js"></script>`.

  Hay mucho más que aprender, pero nos enfocaremos en el lenguaje.
</details>