# AGENTS.md

## 1. Descripción del proyecto

Landing page de una sola página, en español, para un arquitecto-artista especializado en casas de campo de madera, acero y vidrio.
Presenta su identidad, trabajo, trayectoria y próximas exposiciones y conferencias mediante cuatro secciones enlazadas desde la navegación.
La experiencia debe transmitir su sensibilidad arquitectónica y artística, con una presentación visual cuidada y accesible.

## 2. Archivos del proyecto

- **A01:** `index.html`: estructura semántica, contenido, metadatos y datos estructurados de la página.
- **A02:** `styles.css`: todos los estilos, estados de interacción y media queries. Enlazarlo desde `index.html`; no usar estilos inline ni bloques `style`.
- **A03:** `img/`: crear esta carpeta solo si se utilizan imágenes; guardar allí los recursos locales, optimizados y con nombres descriptivos.
- **A04:** No generar otros archivos de implementación ni modificar archivos ajenos al alcance sin autorización expresa.
- **A05:** En la tarea actual, crear exclusivamente `AGENTS.md`. Esta especificación no autoriza implementar la web ni crear `index.html`, `styles.css` o `img/`.

## 3. Reglas obligatorias

### Tecnología y estructura

- **R01:** Usar solo HTML y CSS. Prohibidos JavaScript ejecutable, manejadores de eventos inline, frameworks, librerías externas, CDN y dependencias de frontend. La única etiqueta `script` permitida es `type="application/ld+json"` para datos estructurados no ejecutables.
- **R02:** Escribir HTML bien formateado: sangría consistente de dos espacios, etiquetas correctamente anidadas y cerradas, atributos entre comillas, identificadores únicos y ausencia de elementos obsoletos.
- **R03:** Aplicar HTML semántico estricto: `header` para la cabecera, `nav` para la navegación, `main` único para el contenido principal, `section` para cada bloque temático, `article` para cada proyecto o evento autónomo cuando exista y `footer` para el cierre. No sustituir estos elementos por contenedores genéricos cuando corresponda su significado.
- **R04:** Mantener una jerarquía lógica: un solo `h1` con el nombre del artista en Portada; `h2` en cada sección restante y `h3` para proyectos o eventos subordinados. No saltar niveles ni elegir encabezados por su apariencia; cada `section` debe tener un encabezado que la identifique.

### Diseño y contenido del artista

- **R05:** Incluir navegación con los textos Portada, Sobre mí, Trayectoria y Próximas exposiciones y conferencias. Usar enlaces internos a `#portada`, `#sobre-mi`, `#trayectoria` y `#proximos-eventos`, respectivamente; los identificadores deben existir en las cuatro secciones.
- **R06:** Cada sección debe ocupar aproximadamente una pantalla mediante `min-height: 100vh` y, como mejora compatible, `min-height: 100svh`. Permitir que crezca con su contenido; no imponer alturas fijas que recorten texto. Si la navegación es fija, compensar su altura y usar `scroll-margin-top` para no ocultar encabezados al seguir enlaces.
- **R07:** Definir todo el CSS en `styles.css`. Usar Flexbox como sistema de maquetación y un enfoque mobile-first, con media queries para adaptar columnas, espacios y navegación a pantallas mayores. La navegación debe funcionar sin JavaScript, poder envolver sus enlaces y no causar desplazamiento horizontal.
- **R08:** Crear una estética contemporánea y coherente con la arquitectura rural de madera, acero y vidrio: tipografía legible, escala tipográfica consistente, espacio en blanco, paleta con contraste y fotografías reales de proyectos cuando estén disponibles. Usar variables CSS para colores y espaciado; evitar decoración que compita con la obra y mantener estados de enlace y foco visibles.
- **R09:** Portada da la bienvenida e identifica al artista y su especialidad; Sobre mí presenta su biografía y enfoque; Trayectoria recoge hitos y proyectos; Próximas exposiciones y conferencias muestra eventos confirmados con nombre, fecha, lugar y enlace cuando exista. Mantener el protagonismo de las casas de campo de madera, acero y vidrio. No inventar identidad, premios, obras, ubicaciones, fechas ni eventos; pedir los datos faltantes y omitir afirmaciones no verificadas.

### Accesibilidad

- **R10:** Declarar `lang="es"` en `html`, codificación UTF-8 y meta viewport. Incluir `aria-label` descriptivo en `nav`, un enlace para saltar al contenido principal y nombres comprensibles en todos los enlaces. Priorizar semántica nativa y un orden de lectura y tabulación coherente para lectores de pantalla y teclado.
- **R11:** Todas las imágenes de contenido deben tener `alt` descriptivo que explique la obra o información relevante. Solo las imágenes puramente decorativas deben llevar `alt=""` para que no generen ruido en lectores de pantalla; no usar imágenes de fondo para transmitir información esencial.
- **R12:** Cumplir contraste WCAG AA: al menos 4.5:1 para texto normal y 3:1 para texto grande y componentes relevantes. No depender solo del color; conservar indicadores de foco y legibilidad al ampliar el texto al 200 %. Si hay animación o desplazamiento suave, respetar `prefers-reduced-motion`.

### SEO, Schema.org y GEO

- **R13:** Incluir un `title` específico y una meta description factual. Incorporar Open Graph con `og:title`, `og:description` y `og:type`; añadir `og:url`, `og:image` y `og:image:alt` cuando existan una URL pública y una imagen reales. No publicar dominios, imágenes o enlaces ficticios.
- **R14:** Incluir JSON-LD válido de Schema.org con `@context: "https://schema.org"` y una entidad `Person` que describa al artista con datos confirmados, como `name`, `jobTitle`, `description`, `url` o `sameAs` cuando se conozcan. Agregar `CreativeWork` para obras documentadas y `Event` para exposiciones o conferencias confirmadas, si aplica, relacionados con la persona mediante `creator`, `performer` u otra propiedad apropiada. Los datos deben coincidir con el contenido visible; omitir campos desconocidos y validar el JSON sin comentarios ni comas finales.
- **R15:** Para GEO, redactar frases claras, autosuficientes y factuales que una IA pueda citar: quién es, qué hace y dónde trabaja, con ciudad o región confirmada. Mantener nombres, materiales, lugares y fechas consistentes entre contenido, metadatos y JSON-LD; usar fechas explícitas y `time` con `datetime` cuando proceda. Evitar superlativos sin evidencia y texto oculto para buscadores.

## 4. Pasos antes de cada commit

1. **C01:** Revisar `git status` y `git diff` para confirmar el alcance autorizado, conservar cambios previos del usuario y comprobar que ningún archivo protegido fue alterado. En la tarea actual, el único archivo nuevo o modificado debe ser `AGENTS.md`.
2. **C02:** Comprobar las reglas de este documento. Cuando exista la web y su implementación esté autorizada, validar HTML con el validador W3C y CSS con su validador correspondiente; corregir errores de formato, anidamiento, identificadores y jerarquía de encabezados.
3. **C03:** Cuando exista la web, probar enlaces internos y disposición en móvil y escritorio, incluyendo 320 px de ancho y ampliación al 200 %; verificar que no haya recortes, solapamientos ni desplazamiento horizontal.
4. **C04:** Cuando exista la web, recorrerla solo con teclado y revisar sus regiones y encabezados con un lector de pantalla; comprobar enlace de salto, foco visible, `aria-label`, textos alternativos y contraste.
5. **C05:** Cuando exista la web, revisar `title`, description, Open Graph y exactitud factual; validar la sintaxis JSON-LD y sus entidades con Schema Markup Validator, y contrastarlas con la información visible y confirmada del artista.
6. **C06:** Ejecutar `git diff --check`, revisar el diff final y confirmar que no se incorporaron JavaScript ejecutable, dependencias, secretos ni archivos fuera de alcance. Registrar las comprobaciones no realizadas y su motivo; no crear un commit salvo solicitud expresa del usuario.

Los pasos que requieren la web no aplican mientras solo se redacta este documento; no crear archivos para poder ejecutarlos.

## 5. Archivos protegidos

- **P01:** No modificar, eliminar ni renombrar `README.md`, `README.es.md`, `README.cn.md`, `learn.json` o `server.py`.
- **P02:** No alterar `.git/`, `.vscode/`, configuraciones existentes, archivos de instrucciones adicionales, secretos ni credenciales. No crear ramas ni commits sin solicitud expresa.
- **P03:** Preservar todos los cambios previos del usuario, aunque afecten a archivos de trabajo permitidos; nunca revertirlos para facilitar la tarea.
- **P04:** Después de su creación, no modificar este `AGENTS.md` sin autorización expresa. Si una tarea requiere tocar un archivo protegido, detener esa parte del trabajo y solicitar permiso antes de editarlo.