# Sitio web de Emilio Tejeda

Este repositorio contiene el sitio web personal y academico de Emilio Tejeda, construido con Jekyll y publicado con GitHub Pages. Esta guia explica como editar el contenido sin necesidad de saber programar.

## Como funciona

Cada pagina del sitio es un archivo de texto (.md) dentro de este repositorio:

- index.md -> Home
- investigacion.md -> Investigacion
- docencia.md -> Docencia
- divulgacion.md -> Divulgacion

Cuando editas cualquiera de estos archivos y le das "Commit changes", GitHub reconstruye el sitio automaticamente. El proceso tarda entre 30 segundos y 2 minutos. Puedes ver el progreso en la pestana "Actions" del repositorio (un circulo amarillo en progreso se pone verde cuando termina). Si despues de eso no ves el cambio, presiona Ctrl+Shift+R (o Cmd+Shift+R en Mac) en el navegador para forzar que se vea la version mas reciente sin cache.

## Como editar texto

1. Entra al archivo .md de la pagina que quieres cambiar.
2. Da clic en el lapiz (icono de editar) arriba a la derecha.
3. Cambia el texto que necesites.
4. Baja hasta el boton verde "Commit changes" y dale clic (aparece dos veces, la segunda vez confirma el guardado).
Nota: el editor de GitHub a veces cierra automaticamente etiquetas HTML (por ejemplo, al escribir `<div>` agrega solo el `</div>` por su cuenta). Si ves texto duplicado como `</style>style>` despues de escribir algo con < y >, simplemente borra la parte de sobra con Backspace. No es un error tuyo, es el editor.
## Como cambiar o agregar imagenes

Las imagenes viven en la carpeta assets/images. Para subir una nueva:

1. Entra a esa carpeta en el repositorio.
2. Boton "Add file" -> "Upload files".
3. Arrastra el archivo (o varios a la vez).
4. Baja y dale clic a "Commit changes" (este paso se olvida facil, si no le das clic la imagen no se guarda).

Medidas recomendadas segun el tipo de imagen:

- Banner de cada pagina (Home, Investigacion, Docencia, Divulgacion): 1600 x 450 px, formato panoramico.
- Foto de perfil (circulo en la barra lateral): 400 x 400 px, cuadrada, con la cara centrada.
- Logos pequenos (como los de Divulgacion): no importa mucho el tamano original, se ajustan con CSS, pero entre 200 y 400px de ancho es suficiente.

Una vez subida la imagen, para usarla en una pagina hay que escribir esto en el archivo .md correspondiente, donde quieras que aparezca:
`![texto descriptivo de la imagen](/e-tejeda.github.io/assets/images/NOMBRE-DEL-ARCHIVO.png){: style="width:100%;max-height:280px;object-fit:cover;border-radius:6px;" }`
Importante: la ruta siempre debe empezar con /e-tejeda.github.io/assets/images/ (no solo /assets/images/). Esto es por un comportamiento particular de Jekyll en este sitio -- si se omite ese prefijo, la imagen no carga en Investigacion, Docencia ni Divulgacion (aunque si carga en Home). Usa siempre la version completa para evitar el problema.

## Como cambiar el CV, temarios o notas de curso (PDFs)

Estos archivos NO viven en este repositorio, viven en Google Drive, y el sitio solo tiene el link. Esto es a proposito, para que sea facil actualizarlos sin tocar codigo.

Para reemplazar un PDF sin romper el link del sitio:

1. Abre el archivo en Google Drive.
2. Menu de arriba -> "Archivo" -> "Administrar versiones" (o el icono de reloj/historial).
3. Sube la nueva version del archivo AHI, no subas un archivo nuevo por separado.

Si subes un archivo nuevo en vez de una nueva version del mismo, el link cambia y se rompe en el sitio.

## Ajustes de diseno (colores, tamanos de letra, etc.)

Todo el diseno personalizado del sitio esta en un solo archivo: _includes/head/custom.html. Ahi estan las reglas de color de la barra lateral, tamanos de texto, botones, etc. Cada regla es una linea que empieza con un punto (por ejemplo .sidebar.sticky) seguida de instrucciones entre llaves { }.

Para cambios pequenos (un tamano de letra, un color), generalmente basta con encontrar la regla correspondiente y cambiar el numero o el codigo de color (por ejemplo #2F4B8C), sin tocar el resto de la linea.

## Problemas comunes

- "Subi una imagen pero no aparece": revisa que le hayas dado clic a "Commit changes" despues de subirla, y que la ruta en el .md tenga el prefijo completo /e-tejeda.github.io/assets/images/.
- "Cambie algo y no se ve": espera a que el circulo en la pestana Actions se ponga verde, y luego refresca con Ctrl+Shift+R.
- "El link de un PDF ya no funciona": probablemente se subio un archivo nuevo en Drive en vez de una nueva version del mismo archivo. Hay que actualizar el link en el .md correspondiente con el link nuevo.
