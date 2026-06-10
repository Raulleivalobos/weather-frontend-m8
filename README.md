# ClimaCL - Plataforma Meteorológica 🌤️ (Módulo 8)

Aplicación web de pronóstico meteorológico para 10 ciudades de Chile. Esta versión integra un sistema completo de autenticación, protección de rutas y consumo de APIs mediante Axios, gestionando el estado global con Pinia. Además, incorpora mejoras avanzadas de UI/UX, seguridad y persistencia de datos por usuario.

## 🔗 Enlace al Repositorio

**GitHub:** https://github.com/Raulleivalobos/weather-frontend-m8

---

## 👤 Sistema de Usuarios y Seguridad

El proyecto utiliza **Firebase Authentication** para gestionar el registro y acceso de forma segura.

- **Seguridad de Contraseñas:** El formulario de registro incluye validación mediante Expresiones Regulares (Regex) que exige un mínimo de 8 caracteres, combinando letras, números y símbolos.
- **Identificador Único (UID):** Un token seguro generado por Firebase para identificar la sesión de cada usuario de forma individual.

---

## 💾 Persistencia de Datos y Preferencias (LocalStorage)

A diferencia de versiones anteriores, el estado global gestionado por Pinia ahora está vinculado al `UID` del usuario y respaldado en el `LocalStorage` del navegador. Cada usuario tiene su propia configuración guardada:

- **Favoritos:** Arreglo numérico con los IDs de sus ciudades favoritas para mantener sus preferencias de filtrado entre sesiones.
- **Preferencias Visuales y de Unidad:** El usuario puede alternar la temperatura entre grados Celsius (°C) y Fahrenheit (°F), y cambiar la interfaz entre un Tema Claro y un Tema Oscuro.

---

## 🛣️ Rutas y Autenticación (Vue Router)

El sistema cuenta con rutas protegidas mediante _Navigation Guards_ (`beforeEach`) para garantizar que solo los usuarios registrados puedan acceder a la información:

**Rutas Públicas (Con video de fondo dinámico y efecto Glassmorphism):**

- `/login` : Vista para que los usuarios existentes inicien sesión.
- `/registro` : Vista con el formulario para crear una cuenta nueva y validación de seguridad.

**Rutas Privadas (Requieren Autenticación):**

- `/` (Home) : Panel principal donde se listan las 10 ciudades de Chile con imágenes representativas. Permite buscar por texto y filtrar por favoritos.
- `/detalle/:id` : Vista de pronóstico extendido semanal con estadísticas de temperaturas.
- `/preferencias` : Panel de control individual para ajustar unidades de medida y tema visual.

_(Si un usuario no logueado intenta acceder a rutas privadas, es redirigido automáticamente al `/login`)._

---

## ⚙️ Instrucciones de Ejecución

Sigue estos pasos para levantar el proyecto en tu entorno local:

1. Clonar el repositorio:

```bash
   git clone [https://github.com/Raulleivalobos/weather-frontend-m8.git](https://github.com/Raulleivalobos/weather-frontend-m8.git)

2. Navegar a la carpeta del proyecto:

cd weather-frontend-m8

3. Instalar las dependencias (Se recomienda utilizar pnpm):

pnpm install

4. Levantar el servidor de desarrollo:

pnpm dev

El proyecto estará disponible en tu navegador, generalmente en http://localhost:5173.

Desarrollado por Raúl Leiva Lobos - 2026
```
