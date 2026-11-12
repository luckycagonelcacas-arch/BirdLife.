# BirdLife – Virtual Birds

Proyecto inicial jugable para Android, empaquetado con Capacitor y GitHub Actions.

## Incluido

- Juego autocontenido en `www/index.html` (HTML, CSS y JavaScript en un solo archivo).
- Interfaz móvil adaptable y navegación entre pantallas.
- Ocho especies desbloqueables, colección y selección de ave.
- Necesidades: hambre, felicidad, energía, higiene, salud y confianza.
- Acciones de cuidado, tienda, monedas, inventario y cofre.
- Hábitats descriptivos por especie.
- Simulación sencilla de tiempo fuera de la aplicación y recompensas offline.
- Sistema de pareja, nido y nacimiento de crías de demostración.
- Guardado local en el dispositivo.
- Configuración Capacitor y GitHub Actions para compilar APK de depuración.

## Importante: alcance real de esta versión

Esta entrega es una **primera versión jugable 2D**, no el simulador 3D final. Los sonidos son tonos sintéticos de prueba, no grabaciones de aves reales. La reproducción, genética y crecimiento son simplificados. No hay todavía cuentas, sincronización en la nube, notificaciones push fiables ni ejecución permanente en segundo plano. La simulación del tiempo transcurrido se actualiza al volver a abrir la aplicación. El guardado es local y no se comparte entre dispositivos.

## Subir a GitHub sin reemplazar archivos uno por uno

1. Descomprime el ZIP completo.
2. Crea un repositorio vacío llamado `BirdLife-Virtual-Birds`.
3. Sube **todo el contenido de esta carpeta de una sola vez**, manteniendo la carpeta oculta `.github`.
4. Confirma los cambios en la rama `main`.
5. Abre la pestaña **Actions**. El flujo `Build BirdLife APK` compilará el APK automáticamente. También puedes ejecutarlo manualmente con **Run workflow**.
6. Abre la ejecución terminada y descarga el artefacto `BirdLife-debug-apk`. Dentro estará `app-debug.apk`.

## Compilar localmente

Requiere Node.js 20, Java 17 y Android SDK:

```bash
npm install
npx cap add android
npx cap sync android
cd android
./gradlew assembleDebug
```

El APK de depuración queda en `android/app/build/outputs/apk/debug/app-debug.apk`.

## Publicación

El flujo produce un APK de depuración para pruebas. Para Google Play hace falta una compilación release firmada y completar los requisitos vigentes de publicación.

## Estructura

```text
.github/workflows/android.yml
www/index.html
capacitor.config.json
package.json
.gitignore
README.md
```
