# AudioShare BT — Descargas

Instaladores listos de **AudioShare**: comparte el audio de un dispositivo a otro por **Wi-Fi, a través de un Hotspot** (sin necesidad de router ni internet), con baja latencia (Opus + corrección de errores FEC + jitter buffer adaptativo).

Este repositorio es solo de **distribución**: trae los instaladores ya compilados, listos para instalar. El código fuente completo, la documentación técnica y el historial de desarrollo están en el repositorio privado del autor.

## Descargar

| Plataforma | Archivo | Notas |
|---|---|---|
| **Android** | [`APK/AudioShare.apk`](APK/AudioShare.apk) | Android 7+ (el audio del sistema requiere Android 10+). Ver [`APK/LEEME.txt`](APK/LEEME.txt). |
| **Windows** | [`AudioShare-Windows.zip`](AudioShare-Windows.zip) | Descomprime y abre `AudioShare\AudioShare.exe`. No necesita Python. |

También puedes descargarlos desde la pestaña **[Releases](../../releases)**.

## Cómo usarla

Uno de los dos equipos **crea su Hotspot** y el otro se conecta a él (por Wi-Fi normal, con router, no funciona — es por diseño).

1. En el equipo que va a **transmitir**: modo *Servidor* → *Iniciar transmisión*. Pon algo a sonar.
2. En el equipo que va a **recibir**: modo *Cliente* → *Buscar y Conectar*.

La antena roja parpadeando significa "esperando"; verde, "conectado"; las flechas azules en cascada, "audio fluyendo".

> **Android**: está firmado con la clave de *debug* de Flutter, así que Android pedirá permitir "instalar apps desconocidas" — es normal, no es una señal de que el APK esté alterado (puedes verificar su SHA-256 en `APK/LEEME.txt`).
>
> **Windows**: la primera vez, el Firewall preguntará si permites `AudioShare.exe` en la red. Acepta en redes **Privadas y Públicas** (el hotspot suele detectarse como red Privada); si lo bloqueas, no conectará.

## Solución de problemas

- **"No se encontró el emisor"**: confirma que un equipo tiene su Hotspot prendido y el otro está conectado a **ese** hotspot (no al Wi-Fi de un router), y que el emisor ya inició la transmisión.
- **Conecta pero no se oye nada**: en Windows, la captura no genera audio si no hay nada sonando. En Android, algunas apps (Netflix, Disney+, etc.) bloquean la captura de su propio audio por DRM.
- **"LLENO"**: cada intento ocupa un lugar en el emisor hasta ~8 s tras desconectarse; espera unos segundos entre intentos (máximo 4 receptores a la vez).
- **En Windows dice que el puerto está en uso**: hay otra ventana de AudioShare abierta; ciérrala (solo puede haber una a la vez).

## Licencia

Sin licencia definida todavía (todos los derechos reservados por el autor hasta que se elija una).
