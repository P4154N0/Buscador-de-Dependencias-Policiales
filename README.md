# Buscador-de-Dependencias-Policiales

# 📍 Buscador de Dependencias Policiales - PBA

Este proyecto es una herramienta interactiva diseñada para la visualización y localización de dependencias policiales en la Provincia de Buenos Aires. Permite filtrar por partido, visualizar la ubicación exacta en un mapa interactivo y obtener información de contacto rápida.

Desarrollado para **Centro de Despacho Coronel Suárez**.

## 🚀 Características

-   **Mapa Interactivo:** Utiliza la librería **Leaflet.js** para mostrar pines dinámicos sobre OpenStreetMap.
-   **Filtro Inteligente:** Selector de partidos que carga dinámicamente desde un archivo JSON.
-   **Diseño Responsivo:** Interfaz optimizada para monitores grandes y dispositivos móviles.
-   **Fichas Informativas:** Listado detallado con Teléfono, Dirección y Localidad de cada dependencia.
-   **Escalabilidad:** Separación clara entre la lógica de visualización y la base de datos (`datos.json`).

## 🛠️ Tecnologías utilizadas

* **HTML5 / CSS3:** Maquetación moderna con Flexbox y CSS Grid.
* **JavaScript (ES6+):** Manipulación del DOM, Fetch API para carga de datos y lógica asíncrona.
* **Leaflet.js:** Biblioteca de mapas interactivos de código abierto.
* **JSON:** Estructura de almacenamiento de datos ligera.

## 📁 Estructura del Proyecto

```text
/
├── index.html          # Estructura principal y lógica JS
├── datos.json          # Base de datos de las dependencias
└── img/                # Carpeta para recursos visuales
    └── logo.png        # Logo institucional de la Superintendencia.
```

## ⚙️ Detalles Técnicos de Funcionamiento

El núcleo de la aplicación se basa en el procesamiento asíncrono de datos y la manipulación dinámica del mapa. A continuación, se detalla el flujo lógico:

### 1. Carga de Datos (Fetch API)
Al iniciar la página, se dispara una función `async/await` que consume el archivo `datos.json`. Los datos se almacenan en una variable global para evitar múltiples peticiones al servidor, optimizando el rendimiento.

### 2. Normalización de Partidos
Para evitar duplicados en el selector (Combo Box), se utiliza el objeto `Set` de JavaScript:
```javascript
const partidosUnicos = [...new Set(dependencias.map(d => d.PARTIDO))];
```

## 👨‍💻 Autor
Desarrollado con 🧉 y dedicación por: Héctor Pablo Graff (P4154N0)
