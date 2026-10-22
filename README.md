# AudioShare BT — Descargas

Instaladores listos de **AudioShare**: comparte el audio de un celular o una PC hasta con **4 receptores**, **sin internet, sin módem y sin señal**, con baja latencia (Opus + corrección de errores FEC + reproductor de baja latencia) y **audio cifrado**.

Este repositorio es solo de **distribución**: trae los instaladores ya compilados, listos para instalar. El código fuente completo, la documentación técnica y el historial de desarrollo están en el repositorio privado del autor.

## Descargar

| Plataforma | Archivo | Notas |
|---|---|---|
| **Android** | [`APK/AudioShare.apk`](APK/AudioShare.apk) | Android 7+ (audio del sistema y red propia: Android 10+). Ver [`APK/LEEME.txt`](APK/LEEME.txt). |
| **Windows** | [`AudioShare-Windows.zip`](AudioShare-Windows.zip) | Descomprime y abre `AudioShare\AudioShare.exe`. No necesita Python. |

También puedes descargarlos desde la pestaña **[Releases](../../releases)**.

## Cómo usarla

**Compartir** (celular o PC):
1. Toca **Compartir** y elige **Red propia** (el equipo crea su propia red, sin internet; el audio va directo y con menos retraso) o **Wi-Fi de casa** (todos en el mismo Wi-Fi).
2. Aparece un **QR**. Debajo, la lista de quién está escuchando (máximo 4), con botón para sacar a alguien.

**Escuchar**:
- **Celular**: toca **Escuchar**. Salen solos los equipos que comparten cerca → **Unirse** → el que comparte acepta el **número de 6 dígitos**. O toca «¿Deseas escanear el QR?».
- **PC**: toca **Conectar** → **Unirse** junto al equipo que comparte → acepta el número en ese equipo.

Solo aparecen equipos con AudioShare (redes «DIRECT-AS-…»). **Nadie escucha sin el QR o sin que lo acepten**: el audio va cifrado con una clave nueva en cada sesión.

**Hotspot manual** (como antes): un equipo prende su Hotspot en los ajustes y el otro se conecta; sin QR ni cifrado.

> **Android**: está firmado con la clave de *debug* de Flutter, así que Android pedirá permitir "instalar apps desconocidas" — es normal (puedes verificar su SHA-256 en `APK/LEEME.txt`). Para ver los equipos cercanos, Android pide «Dispositivos cercanos» y «Ubicación»: AudioShare no usa tu ubicación, solo ve las redes.
>
> **Windows**: la primera vez, el Firewall preguntará si permites `AudioShare.exe` en la red. Acepta en redes **Privadas y Públicas**; si lo bloqueas, no conectará. Para crear la red propia o unirse a una, la PC necesita Wi-Fi.

## Solución de problemas

- **No aparece el equipo que comparte**: confirma que eligió **Red propia** y toca **Buscar**. En el celular, acepta los permisos de dispositivos cercanos y ubicación.
- **Conecta pero no se oye nada**: en el equipo que comparte tiene que estar sonando algo. En Android, algunas apps (Netflix, Disney+, etc.) bloquean la captura de su propio audio por DRM.
- **Por «Wi-Fi de casa» va con más retraso**: es el módem. Con **Red propia** el audio va directo.
- **"Ya hay 4 personas escuchando"**: es el máximo; que alguien salga o lo saquen.
- **En Windows dice que el puerto está en uso**: hay otra ventana de AudioShare abierta; ciérrala.

## Licencia

Sin licencia definida todavía (todos los derechos reservados por el autor hasta que se elija una).
