# Avante Project - Gestión de Propiedades
Sistema de gestión inmobiliaria basado en WordPress diseñado para la integración dinámica de propiedades, sincronización externa y análisis de datos avanzado.

## Descripción
Este proyecto permite a una inmobiliaria gestionar su catálogo de propiedades de forma híbrida. El sistema se sincroniza con la API de EasyBroker para obtener las propiedades de manera automatizada, manteniendo la capacidad de almacenarlas, editarlas y expandirlas localmente. Incluye un panel de control avanzado para la visualización de estadísticas y métricas del inventario.

## Motor Inmobiliario (Real Estate Engine)
El núcleo del proyecto está diseñado específicamente para el mercado de bienes raíces con capacidades de alto rendimiento:

- **Integración con EasyBroker API:** Sincronización completa de propiedades, incluyendo metadatos, descripciones enriquecidas y galerías de imágenes.
- **Gestión Híbrida de Inventario:** Infraestructura para el almacenamiento y edición personalizada de propiedades en la base de datos local (CPT Property).
- **Dashboard de Estadísticas:** Panel administrativo integrado en WordPress que ofrece una vista panorámica del inventario:
    - Métricas de estado (publicadas, borradores, privadas).
    - Desglose por tipo de operación (Venta/Renta).
    - Estadísticas por tipo de propiedad y ubicación.
    - Estado y log de la última sincronización.
- **Filtrado AJAX Avanzado:** Sistema de búsqueda en tiempo real que permite navegar por el catálogo mediante:
    - Ubicación (Estado y Ciudad).
    - Tipo de Operación y Tipo de Propiedad.
    - Rangos de precio y dimensiones (construcción/terreno).
- **Galería Inteligente:** Gestión unificada que combina imágenes de la API con archivos locales subidos mediante ACF.
- **Acciones Rápidas (CTA):** Conversión automática de datos de contacto (WhatsApp, Teléfono, Email) en botones de acción directa en las fichas.

## Funcionalidades del Tema (Frontend & UX)
Maquetación moderna enfocada en el rendimiento y la experiencia de usuario:

- **Optimización y Rendimiento:**
    - Carga Condicional de Recursos: Los assets (JS/CSS) se cargan solo en las vistas donde son necesarios.
    - Sistema de Iconos SVG: Integración nativa en PHP para evitar peticiones HTTP adicionales.
    - SEO Estructural: Estructura semántica HTML5 y soporte nativo para Google Tag Manager.
- **Experiencia de Usuario:**
    - Diseño "Mobile-First" con CSS moderno (Nesting, Variables) y `theme.json`.
    - Modo Noche Nativo: Activación automática basada en la preferencia del sistema operativo del usuario.
    - Navegación Refinada: Migas de pan (breadcrumbs) dinámicas y paginación numérica.
- **Soporte de Contenidos:**
    - Formatos de Post Personalizados: Estilos específicos para Galerías (con Slider y Lightbox), Video, Citas, Enlaces y más.
    - Bloques Gutenberg a Medida: Renderizado personalizado para galerías interactivas y formularios de búsqueda.

## Estructura del Proyecto
```text
avante-project/
├── assets/                     # Recursos estáticos (CSS modular, JS, Iconos)
├── inc/                        # Lógica modular
│   ├── core.php                # Configuración principal y encolado de assets
│   ├── real-estate-tools.php   # Lógica de filtros y panel de control de propiedades
│   ├── easybroker-sync.php     # Integración y sincronización con la API
├── template-parts/             # Fragmentos de plantilla reutilizables
│   ├── loop/                   # Plantillas para listados (content-property.php)
│   ├── page/                   # Plantillas para páginas estáticas
│   └── single/                 # Plantillas para entradas individuales
├── functions.php               # Punto de entrada de la lógica del tema
├── theme.json                  # Configuración global de estilos y bloques
└── README.md                   # Documentación técnica
```

## Requisitos del Sistema
- WordPress 6.x o superior.
- PHP 8.x o superior.
- API Key de EasyBroker activa.

## Instalación y Configuración
1. Subir el tema a la carpeta `wp-content/themes/` de tu instalación.
2. Activar el tema desde el panel de Administración > Apariencia.
3. Ingresar la API Key de EasyBroker en la sección de ajustes de Propiedades.
4. Ejecutar la sincronización inicial desde el Dashboard de Propiedades.

## Desarrollo y Personalización
- **Lógica:** Toda la funcionalidad crítica reside en `inc/` para mantener `functions.php` organizado.
- **REST API:** El Dashboard consume datos locales mediante la REST API de WordPress para una representación gráfica fluida sin recargas.
- **Estilos:** Se utiliza `style.css` para definir tokens de diseño y variables globales.

## Créditos y Licencia
- **Autor:** ChanoDEV (https://chano.dev)
- **Licencia:** [GNU General Public License v2](https://choosealicense.com/licenses/gpl-2.0/).