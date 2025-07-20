# Dónde se guardan tus datos y cómo los protegemos

En Daenix, priorizamos tu privacidad y la seguridad de tu información. Este documento explica **dónde se almacenan tus datos**, cómo protegemos tu **token de GitHub**, y qué implica esto en cuanto a **portabilidad, rendimiento y seguridad**.

---

## 1. Almacenamiento local y portabilidad

Daenix es una aplicación **portable**. Todos los datos que genera o utiliza se guardan en la misma carpeta donde se encuentra la aplicación. Esto significa que puedes mover toda la carpeta a otro equipo sin necesidad de instalar nada.

Dentro de esa carpeta, Daenix crea un subdirectorio llamado `/data/`, donde guarda:

- **`user.db`**: una base de datos SQLite donde se almacenan datos de navegación local, como el historial de accesos, listas recientes o acciones previas. Esto permite que Daenix funcione de forma más rápida y eficiente.
- **Archivos de configuración**: datos relacionados a tus preferencias, entorno de trabajo y ajustes personalizados.
- **Word space y datos de trabajo**: información relacionada con tus proyectos o sesiones anteriores.
- **`/data/webview2/`**: archivos generados por el motor interno de navegación basado en WebView2, que Daenix utiliza para mostrar contenido dinámico (como documentación, repositorios, vistas web, etc.).

### Opción para no guardar historial

Si lo deseas, puedes desactivar el guardado de datos de navegación desde las preferencias de la aplicación. Esto evitará que se almacene información en `user.db`, pero puede afectar el rendimiento y ciertas funciones que dependen del historial.

---

## 2. Seguridad del token de GitHub

El **token de autenticación de GitHub** se maneja como un dato sensible y **nunca se guarda en texto plano**. En su lugar, utilizamos herramientas de cifrado nativas del sistema operativo para protegerlo.

### ¿Cómo se protege el token?

- **En Windows**: Se utiliza `DPAPI (Data Protection API)` mediante la función `CryptProtectData`. El token queda cifrado y solo puede ser descifrado por el mismo usuario en la misma máquina.
- **En macOS**: El token se guarda en el `Keychain`, el sistema nativo de gestión segura de contraseñas.
- **En Linux**: Se utiliza `Secret Service API`, integrado con sistemas como `GNOME Keyring` o `KDE Wallet`.

Gracias a este sistema, el token:

- Solo puede utilizarse en el mismo equipo y sesión de usuario.
- No puede extraerse ni reutilizarse en otro entorno.
- Se mantiene cifrado, incluso si alguien accede a los archivos de la carpeta `/data/`.

---

## 3. Qué ocurre si borras la carpeta `/data/`

Toda la información de tu sesión se guarda en la carpeta `/data/`. Si decides eliminarla, debes saber lo siguiente:

- **Se perderán tus datos de configuración y navegación.**
- **Se eliminará tu token de acceso a GitHub.**
- **Daenix te pedirá iniciar sesión nuevamente y configurar la aplicación desde cero.**

Borrar esta carpeta puede ser útil si deseas **reiniciar la aplicación completamente** o eliminar cualquier rastro de tu uso anterior. Sin embargo, si lo haces por error, no hay forma automática de recuperar los datos eliminados.

---

## 4. Privacidad y tratamiento de la información

Daenix es una aplicación que se ejecuta completamente de forma local. No recopila, transmite ni almacena datos personales en servidores externos. Las únicas conexiones que realiza son aquellas necesarias para interactuar con servicios como GitHub, según las acciones explícitas del usuario.

No se realiza análisis, recolección ni monitoreo de tus datos por parte de los desarrolladores.

---

## 5. Responsabilidad del usuario

Aunque Daenix implementa medidas de seguridad razonables y buenas prácticas de almacenamiento, el uso correcto y seguro depende del usuario. Recomendamos:

- No compartir la carpeta de Daenix con otras personas sin borrar previamente `/data/`.
- Proteger el acceso físico y digital a tu equipo.
- Cerrar sesión desde el menú si otras personas usan tu mismo ordenador.

---

[Volver a la página principal de ayuda](./index)
