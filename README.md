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

## Marcas compartidas (Firebase)

Fuera de Claude la página usa Firebase Realtime Database (proyecto `el-juicio-tablero`, datos en `tablero/d12`). Todos los que abran el enlace de GitHub Pages ven las marcas en tiempo real; el indicador dice «En vivo · compartido». Si Firebase no responde, la página cae a `localStorage` y dice «Solo en este teléfono».

- Los datos de la versión en Claude y los de Firebase son separados: el equipo debe usar un solo enlace (el de GitHub Pages).
- Las reglas de la base de datos están abiertas para lectura y escritura: cualquiera con el enlace puede marcar. Para cerrar el acceso después del rodaje, cambia las reglas en la consola de Firebase.
