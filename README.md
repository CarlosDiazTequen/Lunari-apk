# Lunari — proyecto para generar el APK

Esta carpeta convierte tu app (el archivo `www/index.html`, que es exactamente
el mismo que ya tienes) en un proyecto Android. GitHub la compila
automáticamente y te entrega un archivo `.apk` listo para instalar en tu
celular. Tú no necesitas instalar Android Studio ni nada en tu computadora.

## Qué hay en esta carpeta

- `www/index.html` → tu app, sin ningún cambio.
- `package.json` y `capacitor.config.json` → la configuración que envuelve
  tu app en un proyecto Android (esto se llama Capacitor).
- `.github/workflows/build-apk.yml` → la receta que le dice a GitHub cómo
  compilar el APK automáticamente cada vez que subas cambios.

## Paso 1 — Crea una cuenta y un repositorio en GitHub

1. Entra a https://github.com y crea una cuenta gratis si no tienes.
2. Arriba a la derecha, toca el "+" → **New repository**.
3. Ponle un nombre, por ejemplo `lunari-app`.
4. Puede ser **público o privado**, cualquiera funciona igual.
5. NO marques "Add a README" (ya tienes uno). Toca **Create repository**.

## Paso 2 — Sube esta carpeta al repositorio

La forma más simple, sin usar la computadora de comandos:

1. En la página de tu repositorio recién creado, busca el link que dice
   **"uploading an existing file"**.
2. Arrastra TODOS los archivos y carpetas de esta carpeta
   (`www`, `.github`, `package.json`, `capacitor.config.json`,
   `.gitignore`, este `README.md`) hacia esa página.
   - Importante: arrastra la carpeta `www` completa y la carpeta `.github`
     completa, no solo los archivos sueltos, para que se mantenga la
     estructura de carpetas.
3. Abajo, escribe un mensaje como "Primera versión" y toca
   **Commit changes**.

## Paso 3 — Espera a que GitHub compile el APK

1. En tu repositorio, toca la pestaña **Actions** (arriba).
2. Vas a ver un proceso llamado "Build Android APK" corriendo (círculo
   amarillo girando). Tarda entre 3 y 6 minutos la primera vez.
3. Cuando el círculo se ponga verde ✓, ya está listo.

## Paso 4 — Descarga el APK

Tienes dos formas de descargarlo, cualquiera sirve:

**Opción A — Releases (más fácil):**
1. En tu repositorio, mira a la derecha de la página principal, busca
   **Releases**.
2. Toca la más reciente ("Lunari - build N").
3. Descarga el archivo `app-debug.apk` desde tu celular (o cópialo a tu
   celular si lo descargaste en la computadora).

**Opción B — Artifacts:**
1. Pestaña **Actions** → toca la ejecución que terminó en verde.
2. Abajo, en "Artifacts", descarga `lunari-debug-apk` (viene comprimido en
   .zip, ábrelo para sacar el .apk).

## Paso 5 — Instala el APK en tu celular

1. Abre el archivo `.apk` descargado desde el explorador de archivos de tu
   celular o desde la notificación de descarga.
2. Android puede pedirte permiso para "instalar apps de origen
   desconocido" (porque no viene de Play Store) — actívalo solo para esta
   instalación.
3. Toca **Instalar**. Listo, ya tienes Lunari como una app normal en tu
   celular, con ícono y todo.

## Cuando hagas cambios más adelante

Cada vez que quieras actualizar la app, solo reemplaza el archivo
`www/index.html` con la nueva versión (arrástralo en GitHub igual que
antes, en la carpeta `www`) y GitHub va a generar un nuevo APK
automáticamente. No hace falta tocar nada más.

## Cosas que puedes personalizar (opcional, no es necesario para que
funcione)

- **Nombre de la app / ícono**: por ahora la app se instala como "Lunari"
  con el ícono genérico de Capacitor. Si más adelante quieres el ícono de
  tu logo, dime y te preparo los pasos.
- **appId**: en `capacitor.config.json` dice `"com.lunari.gestion"` — es
  un identificador interno, no se ve en ningún lado, no hace falta
  cambiarlo.

## Nota sobre internet

La app carga una tipografía decorativa desde Google Fonts la primera vez
que abre con internet disponible. Si no hay internet, usa una tipografía
del sistema en su lugar — todo lo demás (guardar datos, cotizar, vender,
etc.) funciona sin conexión, ya que tus datos se guardan solo en el
celular.
