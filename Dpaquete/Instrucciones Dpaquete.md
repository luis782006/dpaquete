# Instrucciones Dpaquete

## 1. Intención del Proyecto

El objetivo es crear una aplicación nativa para Android TV que permita a los usuarios explorar y reproducir archivos de video (películas, series, etc.) almacenados en un disco duro externo conectado por USB. La aplicación debe ser rápida, funcionar sin conexión a internet (después del escaneo inicial) y ofrecer una experiencia de usuario fluida y adaptada a la navegación con control remoto.

## 2. Arquitectura y Estructura

Para lograr esto, seguiremos una arquitectura moderna y robusta basada en las recomendaciones de Google para aplicaciones de Android.

*   **Interfaz de Usuario (UI):** Usaremos la **biblioteca Leanback de AndroidX**. Es el framework estándar para crear interfaces de TV y nos proporciona componentes como:
    *   `BrowseSupportFragment`: Para la pantalla principal de navegación por categorías (filas).
    *   `CardPresenter`: Para diseñar cómo se ve cada elemento individual (la portada de una película).
*   **Gestión de Datos (Caché local):** Utilizaremos la **biblioteca Room**. Crearemos una base de datos local para guardar la información (metadatos) de los archivos de video, como la ruta al video, la ruta a la portada, el título, etc. Esto hace que la aplicación se cargue instantáneamente sin tener que escanear el disco duro cada vez.
*   **Lógica de Negocio (Escaneo en segundo plano):** Usaremos **WorkManager**. Crearemos un `Worker` que se encargará de escanear el disco duro en segundo plano para encontrar los videos y guardar su información en la base de datos Room.
*   **Reproducción de Video:** Integraremos **ExoPlayer**, la biblioteca recomendada por Google para la reproducción de medios. Es potente, flexible y soporta una gran cantidad de formatos.
*   **Acceso a Archivos:** Implementaremos el **Storage Access Framework (SAF)**. Es la forma moderna y segura que exige Android para que el usuario otorgue permiso a la aplicación para leer un directorio específico, como la raíz del disco duro.

## 3. Plan de Desarrollo (Paso a Paso)

Iremos completando estos pasos juntos. Empezaremos con la configuración inicial.

### **Paso 1: Configuración Fundamental del Proyecto**

El objetivo de este paso es preparar el esqueleto de la aplicación.

*   [ ] **1.1: Añadir Dependencias:**
    *   Actualizar el archivo `gradle/libs.versions.toml` para añadir las versiones de las bibliotecas que usaremos.
    *   Actualizar el archivo `app/build.gradle.kts` para incluir las dependencias de Leanback, Room, WorkManager, ExoPlayer y Glide (para imágenes).

*   [ ] **1.2: Configurar el Manifiesto para TV:**
    *   Abrir `app/src/main/AndroidManifest.xml`.
    *   Declarar que la aplicación es para TV (`android.software.leanback`).
    *   Declarar que no requiere pantalla táctil (`android.hardware.touchscreen`).
    *   Añadir el permiso para leer almacenamiento externo (`READ_EXTERNAL_STORAGE`).

*   [ ] **1.3: Crear la Actividad Principal de TV:**
    *   Crear una `MainActivity.java` que será el punto de entrada.
    *   Configurar esta actividad en el `AndroidManifest.xml` para que aparezca en el launcher de Android TV (usando el intent-filter `LEANBACK_LAUNCHER`).

### **Paso 2: Interfaz de Usuario Básica (Con Datos de Prueba)**

*   *(Pasos futuros a detallar aquí...)*

### **Paso 3: Implementar el Escaneo de Archivos**

*   *(Pasos futuros a detallar aquí...)*

### **Paso 4: Implementar la Reproducción de Video**

*   *(Pasos futuros a detallar aquí...)*
