// Nombre del archivo: worker.js
// Ubicación: En la raíz de tu proyecto (ej. tu-repositorio-github/worker.js)

// IMPORTANTE:
// DEBES COPIAR Y PEGAR EL CONTENIDO COMPLETO DE TU ARCHIVO HTML
// (el que generamos con todas las diapositivas y estilos, llamado "hoja_ruta_ciberseguridad_pdf_interactivo.html" o similar)
// DENTRO DE LAS COMILLAS INVERTIDAS (`) que delimitan la constante `miHtmlCompleto`.
// Reemplaza el comentario " AQUÍ VA TODO TU CÓDIGO HTML " con tu HTML.

const miHtmlCompleto = `

 AQUÍ VA TODO TU CÓDIGO HTML 
 <div class="slide slide-theme-resources">
            <h2><span class="icon-placeholder">[ICONO: Libro Abierto/Comunidad]</span>Diapositiva 14: Recursos Adicionales y Comunidades (Español)</h2>
            <h3><span class="logo-placeholder">[LOGO: Foro]</span>Comunidades y Foros:</h3>
            <ul>
                <li><strong>Foro de Ciberseguridad (Hacking Ético y Seguridad Informática):</strong> Busca foros activos.</li>
                <li><strong>Grupos de Telegram/Discord:</strong> "FluProject", "Adastra", comunidades CTF.</li>
                <li><strong>Reddit:</strong> r/esCiberseguridad, r/hacking_es.</li>
            </ul>
            <h3><span class="logo-placeholder">[LOGO: Podcast]</span>Podcasts en Español:</h3>
            <ul>
                <li><strong>"Desde la Barra del Bar"</strong></li>
                <li><strong>"Ciberseguridad con Cerveza"</strong></li>
                <li><strong>"Hacking Etico y Ciberseguridad"</strong> (Busca similares)</li>
            </ul>
            <h3><span class="logo-placeholder">[LOGO: YouTube]</span>Canales de YouTube Adicionales (Español):</h3>
            <ul>
                <li><strong>FluProject:</strong> <a href="https://www.youtube.com/@FluProject" target="_blank">youtube.com/c/FluProject</a></li>
                <li><strong>Maligno Alonso:</strong> <a href="https://www.youtube.com/@MalignoAlonso" target="_blank">youtube.com/user/MalignoAlonso</a> (Blog y charlas)</li>
                <li><strong>Rootkito:</strong> <a href="https://www.youtube.com/@Rootkito" target="_blank">youtube.com/c/Rootkito</a></li>
            </ul>
        </div>

     </div>
 </body>
 </html>
 -->

`; // FIN DEL HTML PEGADO. Asegúrate de que esta comilla invertida (`) esté al final de tu HTML.

// Este es el objeto que Cloudflare Workers espera por defecto.
export default {
  // La función 'fetch' se ejecuta cada vez que alguien visita tu URL de Worker.
  async fetch(request, env, ctx) {
    // Creamos una nueva respuesta.
    // El primer argumento es el contenido de la respuesta (nuestro HTML completo).
    // El segundo argumento es un objeto con opciones, incluyendo las cabeceras (headers).
    return new Response(miHtmlCompleto, {
      headers: {
        // Esta cabecera le dice al navegador que estamos enviando HTML codificado en UTF-8.
        'Content-Type': 'text/html;charset=UTF-8',
      },
    });
  },
};
```toml
# Nombre del archivo: wrangler.toml
# Ubicación: En la raíz de tu proyecto (ej. tu-repositorio-github/wrangler.toml)

# 'name' es el nombre que tendrá tu Worker en el panel de Cloudflare y
# formará parte de la URL (ej. mi-presentacion-cloudflare.tusubdominio.workers.dev).
# ¡Cámbialo por un nombre único y descriptivo para tu proyecto!
name = "mi-presentacion-cloudflare"

# 'main' especifica el archivo de script principal para tu Worker.
# Debe coincidir con el nombre de tu archivo JavaScript (en este caso, worker.js).
main = "worker.js"

# 'compatibility_date' asegura que tu Worker use una versión específica
# del runtime de Cloudflare Workers, lo que ayuda a evitar que futuras
# actualizaciones rompan tu código inesperadamente.
# Usa una fecha reciente (YYYY-MM-DD).
compatibility_date = "2024-05-16"

# Opcional pero recomendado:
# Si Wrangler tiene problemas para identificar tu cuenta de Cloudflare,
# puedes especificar tu ID de cuenta aquí. Lo encuentras en el panel de Cloudflare.
# account_id = "TU_ID_DE_CUENTA_DE_CLOUDFLARE_VA_AQUÍ"

# No se necesitan 'rules' para módulos de texto ni configuraciones de 'site'
# si incrustas el HTML directamente en la constante 'miHtmlCompleto' en worker.js.
