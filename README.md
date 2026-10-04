# social-media-assets

Medios públicos (imágenes y video) de las publicaciones que programa **Buffer**.
La API de Buffer no recibe archivos: necesita una URL pública, directa y estable que siga viva
hasta la hora de publicación. Este repo cumple esa función y nada más.

Lo gestiona exclusivamente `agents/social_media_agent` (puerta única de publicación).
No subas archivos a mano.

## Estructura

```
AAAA/MM/AAAA-MM-DD_<origen>_<slug>/     una carpeta por publicación (fecha de salida)
    manifest.json                       origen, redes, fecha y archivos
    ig_01.png … ig_NN.png               carrusel de Instagram (orden de publicación)
    reel.mp4, reel_portada.png          Reel 9:16
    card.png                            imagen 1:1 de Facebook y X
marca/                                  portadas y avatar de los perfiles
```

- `<origen>`: `libro_01`, `libro_02` o el proyecto que pidió la publicación.
- La fecha va primero para limpiar y rotar por mes o año sin tocar lo pendiente.
- Nombres en minúsculas, sin espacios ni acentos: la ruta es parte de la URL.

## Reglas

1. **Solo contenido aprobado y listo para salir.** Lo que entra aquí es público desde el push.
2. **Nada se borra antes de publicarse**: Buffer descarga el archivo a la hora programada.
3. **Retención:** lo publicado hace más de 30 días ya no se necesita. Cuando el repo se acerque
   a ~800 MB se limpia (mes a mes) o se rota por año; siempre con aprobación del autor.
4. Sin Git LFS: las URLs de LFS no sirven el archivo directo.
