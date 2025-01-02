# TEMPLATE_DBT_ADS


# Introducción al proyecto

`template_dbt_ads` es un proyecto diseñado para crear una plantilla estándar utilizando Cookiecutter, destinada a generar la estructura básica y archivos principales de un proyecto de DBT orientado al procesamiento de datos de pauta digital.


# Tabla de contenido

- [1. Descripción del proyecto](#1-descripción-del-proyecto)
- [2. Estructura del proyecto](#2-estructura-del-proyecto)
- [3. Instalación](#3-instalación)
- [4. Uso](#4-uso)


# 1. Descripción del proyecto

El proyecto `template_dbt_ads` busca simplificar y estandarizar la creación de proyectos DBT para manejar datos de pauta digital. Utilizando Cookiecutter, genera una estructura predefinida con directorios y archivos esenciales, adaptados a las necesidades específicas de transformación de datos en este dominio. La plantilla incluye configuraciones para macros comunes, modelos de datos en diferentes capas (staging, intermediate y marts) y otros componentes clave, facilitando el desarrollo colaborativo y la escalabilidad.


# 2. Estructura del proyecto

```bash
template_dbt_ads
├── cookiecutter.json             # Archivo de configuración para definir las variables de la plantilla
├── {{cookiecutter.project_slug}} # Directorio raíz del proyecto generado
│   ├── dbt_project.yml           # Configuración principal del proyecto DBT
│   ├── macros                    # Directorio para macros reutilizables
│   │   ├── ads                   # Macros específicas para procesamiento de datos de pauta digital
│   │   ├── client                # Macros personalizadas para clientes
│   │   └── setup                 # Configuraciones iniciales del proyecto
│   │       ├── generate_schema_name.sql # Macro para la generación de nombres de esquemas
│   │       └── generate_schema_name.yml # Documentación de la macro
│   ├── models                    # Directorio para los modelos del proyecto DBT
│   │   ├── groups.yml            # Configuración de grupos de modelos
│   │   ├── intermediate          # Modelos intermedios por fuente
│   │   │   ├── adroll
│   │   │   ├── adsmovil
│   │   │   ├── dv360
│   │   │   ├── google_ads
│   │   │   ├── linkedin_ads
│   │   │   ├── meta_ads
│   │   │   └── tiktok_ads
│   │   ├── marts                 # Modelos finales organizados por área funcional
│   │   │   ├── ads
│   │   │   ├── analysis
│   │   │   ├── financial
│   │   │   └── operation
│   │   └── staging               # Modelos de staging por fuente
│   │       ├── adroll
│   │       ├── adsmovil
│   │       ├── dv360
│   │       ├── google_ads
│   │       ├── linkedin_ads
│   │       ├── meta_ads
│   │       └── tiktok_ads
│   ├── profiles.yml              # Configuración de perfiles DBT
│   ├── seeds                     # Directorio para datos iniciales (seeds)
│   └── test                      # Directorio para pruebas
├── LICENSE                       # Licencia del proyecto
└── README.md                     # Documentación del proyecto
```


# 3. Instalación

### Requisitos previos
- **Python 3.12 o superior**


### Instalación
1. Clonar el repositorio:
   ```bash
   git clone https://github.com/randres2045/template_dbt_ads.git
   cd template_dbt_ads


2. Crear un entorno virtual:
    ```bash
    python -m venv venv
    source venv/bin/activate  # Para Linux/Mac
    venv\Scripts\activate     # Para Windows
    ```

3. Instalar las dependencias:
    ```bash
    pip install -r requirements.txt
    ```


# 4. Uso

### Generación de un nuevo proyecto DBT
1. Ejecutar **Cookiecutter** en el directorio raíz del repositorio:
    ```bash
    cookiecutter .
    ```

2. Completar los parámetros solicitados (e.g., nombre del cliente).


### Personalización
- Editar el archivo `dbt_project.yml` para ajustar las configuraciones generales del proyecto.
- Agregar o modificar macros en el directorio `macros/` según las necesidades del cliente.
- Completar los modelos en `models/` con las transformaciones requeridas.


### Recomendaciones
- Respetar la estructura estándar generada para facilitar la colaboración y el mantenimiento.
- Utilizar el directorio `test` para garantizar la calidad y consistencia de los datos transformados.