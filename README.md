# Firmware del monitor de motor

El equipo (ESP32-S3) consulta este repositorio cuando se le pide (botón de la pantalla, orden MQTT ACTUALIZAR o monitor serie). Desde la 2.2.0 nunca se actualiza solo.

| Archivo | Qué es |
|---|---|
| `version.json` | Versión publicada, tamaño y huella SHA-256 del programa |
| `monitor_motor.ino.bin` | El programa compilado |

El equipo solo instala una versión **mayor** que la suya, y solo si el tamaño y la huella SHA-256 coinciden con `version.json`.

Aquí no hay código fuente ni claves: el programa lee sus claves de la memoria del equipo.

## Publicar una versión nueva

1. Sube `VERSION_FW` en `config.h` y exporta el binario compilado.
2. Calcula la huella y el tamaño del `.bin`.
3. Sube **los dos archivos a la vez**: el `.bin` y el `version.json` con los datos nuevos.
