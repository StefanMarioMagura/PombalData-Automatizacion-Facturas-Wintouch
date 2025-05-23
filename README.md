# 📂 Automatización de Facturas Wintouch

Un script de Python para automatizar la lectura de facturas en PDF y el envío de datos a la API de Wintouch Cloud.

---

## 🎯 Acerca del Proyecto

Este proyecto tiene como objetivo simplificar y automatizar el proceso de gestión de facturas. Lee archivos PDF de facturas, extrae la información relevante y la envía directamente a la plataforma Wintouch Cloud a través de su API REST. Esto reduce la entrada manual de datos, minimiza errores y ahorra tiempo.

Principales funcionalidades:
* Lectura de datos de facturas desde archivos PDF.
* Extracción de campos clave: cliente, NIF/CIF, número de factura, fechas, importes, etc.
* Comunicación con la API REST de Wintouch Cloud.
* Soporte para la gestión de múltiples empresas con configuraciones independientes.

---

## ✨ Características Destacadas

* **Automatización Eficiente:** Procesa múltiples facturas de forma automática.
* **Extracción Precisa:** Diseñado para identificar y extraer los datos correctos de las facturas.
* **Integración Directa:** Conexión sin fisuras con Wintouch Cloud.
* **Configuración Flexible:** Adaptable a diferentes empresas mediante archivos JSON.
* **Modular y Extensible:** Código organizado para facilitar futuras mejoras o adaptaciones.

---

## 🛠️ Tecnologías Utilizadas

* **Python (3.8+)**
* **Bibliotecas Principales:**
    * `requests`: Para las comunicaciones HTTP con la API.
    * `PyPDF2` / `pdfplumber`: Para la manipulación y extracción de datos de PDFs. *(Elige o especifica la que estés usando)*
    * *(Añade cualquier otra biblioteca importante aquí)*

---

## 🗂️ Estructura del Directorio

.
├── main.py                 # Script principal de ejecución
├── config.py               # Configuraciones generales y URLs
├── lector_pdf.py           # Lógica para leer y procesar PDFs
├── enviar_api.py           # Lógica para interactuar con la API de Wintouch
├── empresas/
│   └── empresaX.json       # Configuración específica para la empresa X
├── pdfs/
│   └── empresaX/           # PDFs de facturas para la empresa X
├── requirements.txt        # Dependencias del proyecto
└── .gitignore              # Archivos a ignorar por Git


---

## 🚀 Empezando

Sigue estos pasos para configurar y ejecutar el proyecto en tu entorno local.

### Prerrequisitos

Asegúrate de tener instalado:
* Python (versión 3.8 o superior)
* pip (gestor de paquetes de Python)
* Git (para clonar el repositorio)

### Instalación y Configuración

1.  **Clona el repositorio:**
    ```bash
    git clone [https://github.com/tu-usuario/tu-repositorio.git](https://github.com/tu-usuario/tu-repositorio.git)
    cd tu-repositorio
    ```
    *(Reemplaza con la URL de tu repositorio)*

2.  **Crea y activa un entorno virtual (recomendado):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # En Windows: venv\Scripts\activate
    ```

3.  **Instala las dependencias:**
    ```bash
    pip install -r requirements.txt
    ```
    *(Asegúrate de que `requirements.txt` esté actualizado con todas las bibliotecas necesarias como `requests`, `PyPDF2`/`pdfplumber`)*

4.  **Configura tus empresas:**
    * En la carpeta `empresas/`, crea un archivo `.json` para cada empresa (ej., `nombre_empresa.json`).
    * Edita este archivo con los detalles específicos de la empresa, como tokens de API y otros IDs necesarios. Ejemplo (`empresas/mi_empresa.json`):
        ```json
        {
          "api_token": "TU_API_TOKEN_SECRETO",
          "id_wintouch": "ID_ESPECIFICO_WINTOUCH",
          "directorio_pdf": "nombre_carpeta_pdf"
        }
        ```

5.  **Prepara las carpetas de PDFs:**
    * En la carpeta `pdfs/`, crea una subcarpeta para cada empresa (ej., `pdfs/nombre_carpeta_pdf/` coincidiendo con el valor en el JSON de configuración si lo usas así).
    * Coloca los archivos PDF de las facturas dentro de la carpeta correspondiente de cada empresa.

---

## ▶️ Ejecución

Para procesar las facturas de una empresa específica, ejecuta el script `main.py` desde la raíz del proyecto, indicando la empresa:

```bash
python main.py --empresa nombre_de_la_empresa
Reemplaza nombre_de_la_empresa con el nombre del archivo de configuración de la empresa (sin la extensión .json).
Ejemplo:
Si tienes una configuración en empresas/cliente_uno.json y sus PDFs en pdfs/cliente_uno/:

Bash

python main.py --empresa cliente_uno

---

## ⚠️ Puntos Importantes
Seguridad de Credenciales: Nunca incluyas información sensible como tokens de API directamente en el código fuente que subes a repositorios públicos. Utiliza los archivos de configuración JSON (asegurándote de que estén en .gitignore si contienen datos reales y no plantillas) o variables de entorno.
Estructura de Carpetas: Mantener la estructura de directorios definida es crucial para el funcionamiento del script.
Adaptabilidad: Para nuevas empresas, simplemente replica la estructura de configuración (.json) y la carpeta de PDFs.

---

## 👨‍💻 Autor
Stefan Mario Magura

