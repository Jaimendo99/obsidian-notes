
---
### I. Arquitectura e Infraestructura

*   **Diseño de Arquitectura de la Solución (Semana 1: 2 - 6 de junio)**
    *   Se diseñó la arquitectura de alto nivel de la solución, delineando la interacción entre el **Usuario Final**, la **APLICACIÓN MÓVIL** (Kotlin Multiplatform), el **FRONTEND DE ADMINISTRACIÓN** (Vite.js), el **Backend Ext** (Python) y el **API DEL BACKEND** (Supabase). Toda la comunicación se realiza de forma segura mediante HTTPS.
	
    *![[Pasted image 20250708001505.png]]

*   **Configuración de VPS (Coolify) y Backend (Supabase) (Semana 1: 2 - 6 de junio)**
    *   Se configuró el Servidor Privado Virtual (VPS) utilizando Coolify y se integró con Supabase como servicio de backend. Una instancia del servicio Supabase (`supabase-xgswk4socc008c80ogc4wsw0`) fue configurada en el entorno de producción de Kuna.
    * ![[Pasted image 20250708004033.png]]
	
*   **Configuración de Repositorios (Semana 1: 2 - 6 de junio)**
    *   El repositorio de GitHub `kuna-app` fue estructurado para un proyecto Kotlin Multiplatform, compatible con Android, iOS y Desktop. La distribución de lenguajes del proyecto es aproximadamente 85.4% Kotlin y 14.6% Swift.
	![[Pasted image 20250708004051.png]]

---

### II. Gestión de Datos

*   **Modelo de Entidad-Relación e Implementación de Base de Datos (Semana 1: 2 - 6 de junio)**
    *   Se diseñó e implementó un Diagrama de Entidad-Relación (DER) inicial, cubriendo entidades centrales como `psychologist`, `psychologist_profile_id`, `event_bookings` y `patients`. Esto establece las bases para la estructura de datos de la aplicación.
	![[Pasted image 20250708004113.png]]

*   **Cambios en el MER para el Cuestionario (Semana 2: 9 - 13 de junio)**
    *   Se actualizó el Modelo de Entidad-Relación para una mejor gestión del flujo del cuestionario. Se introdujeron nuevas tablas y relaciones para `questionnaire_answers`, `questionnaire_submissions`, `form_questions`, `question_options` y `patient_profiles`.
	![[Pasted image 20250708004201.png]]

*   **Base de Datos Local para Funcionalidad Offline (Finales de junio)**
    *   Se implementó una solución de base de datos local utilizando Room para Kotlin Multiplatform, lo que permite la funcionalidad offline de la aplicación. Esto incluye `QuestionnaireDao` para el acceso a datos y un constructor `CreateDatabase` configurado para migración destructiva y el controlador SQLite.
	![[Pasted image 20250708004241.png]]

*   **Implementación de Datastore para Datos de Sesión (Finales de junio)**
    *   Se integró DataStore (PreferenceDataStoreFactory) para gestionar y persistir los datos de sesión, mejorando la experiencia del usuario y la gestión del estado de la aplicación.
	![[Pasted image 20250708004308.png]]

---

### III. Autenticación de Usuario

*   **Implementación Inicial de Autenticación en la App (Semana 1: 2 - 6 de junio)**
    *   Se establecieron las estructuras básicas de autenticación dentro de la aplicación móvil, utilizando Kotlin Multiplatform Compose para los elementos de la interfaz de usuario y varios plugins para la compilación y el "hot-reloading".
	![[Pasted image 20250708004341.png]]

*   **Integración de Inicio de Sesión con Google (Semana 2: 9 - 13 de junio)**
    *   Se implementó con éxito el inicio de sesión con Google, cubriendo tanto la configuración del backend (Supabase y Google Cloud) como el desarrollo en la aplicación. Esto incluyó actualizaciones en `build.gradle.kts` para incorporar las librerías de autenticación necesarias.
	![[Pasted image 20250708004416.png]]
	![[Pasted image 20250708004429.png]]

---

### IV. Funcionalidades Principales de la Aplicación

*   **Creación de Navegación Completa de la App y Control de Autenticación (Mediados-Finales de junio: 13 - 27 de junio)**
    *   Se desarrolló el grafo de navegación completo de la aplicación utilizando Jetpack Compose, integrando la inyección de dependencias (Koin) y un robusto control de autenticación. La navegación se adapta dinámicamente según el estado de autenticación del usuario.
	![[Pasted image 20250708004455.png]]
	![[Pasted image 20250708004542.png]]

*   **Vista de Psicólogos con Estilo Tinder (Mediados-Finales de junio: 13 - 27 de junio)**
    *   Se creó una vista de "estilo Tinder" para la coincidencia de psicólogos (`TherapistCardFullHeight`), que presenta perfiles de usuario con imágenes, detalles profesionales, puntajes de compatibilidad y una opción de favorito.
	![[Pasted image 20250708004558.png]]

*   **Inserción de Psicólogos Dummy para Vistas de Discovery (Mediados-Finales de junio: 13 - 27 de junio)**
    *   Se integraron datos de psicólogos ficticios para facilitar el desarrollo y las pruebas de las vistas de Discovery.

*   **Configuración de Repositorios de Psicólogos (Mediados-Finales de junio: 13 - 27 de junio)**
    *   Se configuraron `IMatchRepository` y `MatchRepository` para obtener coincidencias de psicólogos. Actualmente utiliza datos ficticios, pero está configurado para integrarse con Supabase.
	![[Pasted image 20250708004615.png]]

*   **Desarrollo de Pantalla de Cuestionario (Semana 2: 9 - 13 de junio)**
    *   Se lograron avances significativos en las pantallas del cuestionario, permitiendo a los usuarios ingresar información relacionada con sus dificultades y su historial de terapia a través de elementos interactivos de la interfaz de usuario (casillas de verificación, botones de opción).
	![[Pasted image 20250708004639.png]]

*   **Implementación de Datos en Vivo (Finales de junio)**
    *   Se implementó la obtención de datos en vivo para los cuestionarios en el `QuestionnaireRepo`, lo que permite la recuperación dinámica de preguntas y opciones desde Supabase (utilizando el cliente `postgrest`).
	![[Pasted image 20250708004656.png]]

---

Este reporte destaca un mes productivo para el proyecto Kuna, donde se han establecido componentes fundamentales y se han iniciado características clave orientadas al usuario.