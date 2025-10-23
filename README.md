# Restaurante Sabor — Promoción del Día

Este repositorio contiene una página sencilla en HTML/CSS/JS que muestra la "Promoción del Día" de un restaurante ficticio llamado "Restaurante Sabor". Es un proyecto estático pensado como plantilla o ejemplo para mostrar promociones, un pequeño carrusel de platillos y botones de acción.

Contenido principal
- `index.html` — Página única que incluye toda la estructura, estilos y scripts en un solo archivo.

Descripción del funcionamiento

- Hero: sección superior con título, descripción y un botón principal ("Ordenar Ahora") que actualmente muestra una alerta cuando se presiona.
- Beneficios: sección con tres tarjetas que explican ventajas del servicio (entrega rápida, calidad y precios).
- Carrusel de platillos: contiene tres diapositivas (Pizza Deluxe, Hamburguesa Gourmet y Sushi Combo). El carrusel se mueve automáticamente cada 5 segundos y también puede controlarse manualmente con los botones "anterior"/"siguiente" o con los indicadores.

Detalles técnicos

- HTML: estructura semántica con secciones (`<section>`), encabezados y roles ARIA para mejorar accesibilidad.
- CSS: estilos incluidos en el `<head>`; diseño responsivo con media queries para 768px y 480px.
- JavaScript: lógica mínima embebida al final de `index.html`:
	- Control del carrusel (funciones `nextSlide`, `prevSlide`, `goToSlide`, `updateCarousel`).
	- Autoplay con `setInterval` cada 5000 ms y pausa al pasar el cursor sobre el carrusel.
	- Actualización de indicadores y atributos ARIA para indicar la diapositiva activa.
	- Botón de orden que muestra una alerta (sitio para integrar un flujo de pedidos real).

Cómo ejecutar (local)

1. Abrir el archivo `index.html` en cualquier navegador moderno (Chrome, Edge, Firefox, Safari).
2. Si prefieres usar un servidor local (recomendado para evitar restricciones en algunos navegadores):

	 - Usando Python 3 (si está instalado):

		 ```powershell
		 python -m http.server 8000
		 # luego abrir http://localhost:8000
		 ```

	 - Usando una extensión de Live Server en VS Code o cualquier servidor estático.

Cómo personalizar

- Cambiar texto y platillos: editar las diapositivas dentro de `.carousel-track` en `index.html`.
- Agregar/quitar diapositivas: replicar/eliminar bloques `.carousel-slide` y asegurarse de actualizar los indicadores (`.indicator`) correspondientemente.
- Ajustar tiempo de autoplay: modificar el valor `5000` en `setInterval(nextSlide, 5000)` dentro del script.
- Reemplazar las imágenes: actualmente se usan emojis y gradientes; puedes reemplazar el div `.dish-image` por una etiqueta `<img>` y ajustar estilos (altura, border-radius).
- Integrar sistema de pedidos: en el listener del botón `.btn-primary` (al final del archivo) reemplazar la llamada a `alert()` por navegación a un formulario o una API.

Accesibilidad y ARIA

- Se usan roles (`role="banner"`, `role="group"`, `role="contentinfo"`) y atributos ARIA (`aria-roledescription`, `aria-label`, `aria-selected`) para facilitar el uso con lectores de pantalla.
- Indicadores actualizan `aria-selected` para reflejar la diapositiva activa.
- Consideraciones adicionales: agregar controles de teclado (flechas) y mejorar el foco para usuarios de teclado.

Notas de desarrollo

- Proyecto intencionalmente simple y autocontenido en un solo archivo para facilitar su distribución como plantilla.
- No depende de librerías externas.

Próximos pasos sugeridos (opcionales)

1. Mover CSS y JS a archivos separados (`styles.css`, `main.js`) para mejor mantenimiento.
2. Añadir pruebas visuales o snapshots si se integra en un pipeline de CI.
3. Implementar navegación por teclado y soporte de pausado/reescritura más robusto para accesibilidad.

Contacto

Si quieres que adapte este README (por ejemplo, traducciones, instrucciones para despliegue en Netlify/GitHub Pages o separación de archivos), dime qué prefieres y lo hago.
