# Soporte para Lectores de Pantalla

## ¿Qué es un lector de pantalla?

Un **lector de pantalla** es un software que permite a personas ciegas o con baja visión utilizar una computadora a través de **síntesis de voz** o **líneas braille**. El lector interpreta el contenido visual que aparece en pantalla (texto, botones, menús, mensajes, etc.) y lo transforma en **voz hablada o salida braille**, facilitando así la navegación y el uso de programas sin necesidad de ver la pantalla.

Existen diversos lectores de pantalla, pero los más populares en sistemas Windows son **NVDA** (NonVisual Desktop Access) y **JAWS** (Job Access With Speech).

---

## Compatibilidad de Daenix con lectores de pantalla

El soporte para lectores de pantalla en Daenix ha sido **probado únicamente en Windows**, en su versión de **64 bits**, y específicamente con los lectores **NVDA** y **JAWS**.

> **Recomendamos utilizar Daenix con NVDA**, versión **2025.1.2**, que es la versión utilizada en nuestras pruebas de accesibilidad.  
> Se ha verificado que los mensajes, menús, botones y notificaciones son correctamente leídos mediante este lector.

No se garantiza el funcionamiento correcto con versiones anteriores o con otros lectores distintos a los mencionados.

---

## Integración técnica: ¿cómo se comunica Daenix con los lectores?

Para permitir que Daenix pueda leer mensajes directamente con un lector de pantalla, se utiliza una biblioteca llamada **Tolk**. Esta biblioteca actúa como un puente entre la aplicación y los lectores de pantalla instalados en el sistema operativo.

Durante la instalación o uso de Daenix, se crean en la carpeta principal del programa los siguientes archivos:

- `Tolk.dll`: Biblioteca principal para la comunicación con lectores de pantalla.
- `SAAPI64.dll`: Soporte para Speech API.
- `nvdaControllerClient64.dll`: Biblioteca específica para integrarse con NVDA.

Estas bibliotecas permiten que Daenix pueda enviar mensajes directamente al lector de pantalla activo para que sean **anunciados en voz**.

> **Importante:** Estas bibliotecas **solo funcionan en sistemas Windows de 64 bits**. No se ofrece soporte para versiones de 32 bits o para otros sistemas operativos en esta versión.

---

## ¿Se puede desactivar este soporte?

Sí. Si deseas utilizar Daenix sin lector de pantalla, o prefieres que **el lector no lea automáticamente los mensajes del sistema**, puedes desactivar esta función desde:

**Preferencias > Soporte para lector de pantalla**

Al desactivar esta opción, la aplicación dejará de enviar mensajes automáticos al lector. Esta opción puede ser útil para usuarios que utilizan lectores de pantalla de forma parcial, o cuando se desea evitar interferencias en tareas específicas.

---

## ¿Y si uso macOS o Linux?

Actualmente, el soporte de accesibilidad está **limitado a Windows**. Sin embargo, estamos trabajando en ampliar la compatibilidad para usuarios de **macOS y Linux**.

Si deseas ser notificado cuando la versión accesible esté disponible para tu sistema operativo, puedes **apuntarte a nuestra lista de espera** enviando los siguientes datos:

- Nombre completo  
- País  
- Sistema operativo que utilizas (por ejemplo: macOS 14, Ubuntu 22.04, etc.)

---

## Más información

Para conocer las condiciones de uso, limitaciones de soporte técnico y cómo colaborar con el proyecto, puedes consultar el siguiente documento:

[Consulta la licencia y soporte técnico](./license_and_support.md)

Al final de ese documento encontrarás los **datos de contacto oficiales**, donde podrás enviar tus sugerencias o sumarte a futuras pruebas.

---

Este documento se actualiza con cada nueva versión accesible de Daenix. Te agradecemos por formar parte de esta comunidad y por apoyar el desarrollo de software accesible para todas las personas.

---

[Volver a la página principal de ayuda](./index)
