# Palabra Secreta

Juego de lengua para pizarra digital de 2.º de Primaria. Los alumnos siguen las pistas de Lupi, el búho detective, descartan palabras y descubren cuál es la palabra secreta.

Es una aplicación web instalable (PWA): se abre en cualquier navegador, se puede instalar como una app y funciona sin conexión después de la primera visita.

## Publicarla en GitHub Pages

1. Crea un repositorio nuevo en GitHub, por ejemplo `palabra-secreta`. Puede ser público.
2. Sube **todo el contenido de esta carpeta** a la raíz del repositorio (botón *Add file → Upload files* y arrastra los archivos y las carpetas `fonts` e `icons`).
3. Ve a *Settings → Pages*. En *Source* elige *Deploy from a branch*, rama `main` y carpeta `/ (root)`. Guarda.
4. En uno o dos minutos la app estará en `https://TU-USUARIO.github.io/palabra-secreta/`.

## Instalarla en la pizarra

Abre la dirección anterior en Chrome o Edge en el ordenador de la pizarra. Aparecerá el botón **Instalar** en la portada del juego (o el icono de instalar en la barra de direcciones). Desde ese momento se abre a pantalla completa desde su propio icono y funciona sin Internet.

## Actualizarla

Cuando subas cambios, abre `sw.js` y cambia el número de `VERSION` (por ejemplo, de `v1` a `v2`). Así las pizarras que ya la tienen instalada descargan la versión nueva la próxima vez que se abra con conexión.

## Sonido y música

- El botón del altavoz activa o silencia los efectos de sonido (aciertos, fallos, celebraciones).
- El botón de la nota musical activa la música de fondo: un tema alegre en la portada y el mapa, y un tema de detective durante los casos. Está apagada al empezar y el juego recuerda la elección en cada pizarra.
- La música baja de volumen sola mientras se lee una pista en voz alta y cuando se celebra un caso resuelto.
- Toda la música y los sonidos se generan en el propio juego: son originales y funcionan sin conexión.

## Archivos

| Archivo | Para qué sirve |
| --- | --- |
| `index.html` | El juego completo: pantallas, ilustraciones, banco de palabras y lógica. |
| `manifest.webmanifest` | Nombre, colores e iconos de la app instalada. |
| `sw.js` | Guarda el juego en el dispositivo para que funcione sin conexión. |
| `fonts/` | Tipografías Andika y Lilita One (licencia SIL Open Font License). |
| `icons/` | Iconos de la app con Lupi. |
| `.nojekyll` | Indica a GitHub Pages que publique los archivos tal cual. |

## Añadir palabras

El banco de palabras está en `index.html`, dentro de la constante `RAW`. Cada línea es una palabra:

```
palabra|sílabas separadas por guiones|dibujo|tipo|género|número|campo
mariposa|ma-ri-po-sa|mariposa|s|f|sg|animal
correr|co-rrer|-|v
```

- **tipo**: `s` sustantivo, `a` adjetivo, `v` verbo.
- **género**: `m`, `f` o `-`. **número**: `sg`, `pl` o `-`.
- **campo** (solo sustantivos): `animal`, `comida`, `ropa`, `naturaleza`, `transporte` o `cosa`.
- **dibujo**: el nombre de una ilustración existente, o `-` si no tiene. Las palabras sin dibujo solo aparecen en el nivel Inspector o con la opción «Sin dibujos».
