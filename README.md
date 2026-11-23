# Tablero de listos · El Juicio

Tablero de set para seguir quién está listo (vestuario, maquillaje/peluquería y micrófono) por escena y por talento durante el rodaje. Es una sola página, `index.html`, sin dependencias ni paso de compilación.

Vistas: Resumen (todas las escenas), Talentos y extras (todas sus escenas), Por escena y Ajustes (orden de escenas y banco de extras).

## Subirlo a GitHub

1. Crea un repositorio nuevo en GitHub. **Hazlo privado**: la página tiene nombres de talentos y datos del plan de rodaje.
2. En esta carpeta, desde una terminal:

```bash
git init -b main
git add .
git commit -m "Tablero de listos D12"
git remote add origin https://github.com/TU-USUARIO/TU-REPO.git
git push -u origin main
```

Si prefieres no usar terminal: en la página del repositorio, **Add file → Upload files** y arrastra `index.html`, `README.md` y la carpeta `.github`.

## Publicarlo como página web (GitHub Pages)

1. En el repositorio: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
2. Cada vez que hagas un cambio en `main`, el archivo `.github/workflows/pages.yml` lo publica solo.
3. La dirección queda en `https://TU-USUARIO.github.io/TU-REPO/`.

Ojo: GitHub Pages desde un repositorio privado necesita un plan de GitHub que lo permita (Pro, Team o Enterprise). Con el plan gratuito, Pages solo sirve repositorios públicos.

## Trabajarlo en equipo

- Cada persona edita `index.html` en una rama y abre un pull request hacia `main`.
- Para colaborar, agrega a las personas en **Settings → Collaborators**.
- Los datos del plan (escenas, personajes, extras, horas) están al principio del script, bajo el comentario `datos del llamado`. Para un día nuevo, solo se cambian esas listas.

## Importante: las marcas no se comparten desde GitHub Pages

La versión que se publicó en Claude guarda las marcas en una base de datos compartida que solo existe dentro de Claude. Fuera de Claude, la página usa `localStorage`: **cada teléfono ve y guarda solo sus propias marcas**, y nadie ve lo que marcan los demás.

Para tener marcas compartidas en tiempo real fuera de Claude hace falta conectar un servicio de datos (por ejemplo Firebase o Supabase) y cambiar las funciones `write`, `saveCfg` y la sección `conexión compartida` del script. Esas tres partes son las únicas que tocan el almacenamiento.

Mientras tanto, para marcar en equipo y en vivo, usa la versión de Claude (https://claude.ai/artifact/3SCfGsZfAJ4A8sUGMcYL4H) y deja GitHub para versionar el código y publicar la copia web.
