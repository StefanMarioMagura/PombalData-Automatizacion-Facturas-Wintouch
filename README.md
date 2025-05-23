# 📂 Automatización de Facturas Wintouch

Este proyecto automatiza la lectura de datos de facturas en formato PDF y su posterior envío a la plataforma Wintouch Cloud mediante su API REST. Está diseñado para agilizar la gestión de facturación, minimizando errores manuales y optimizando el tiempo.

---

## ✨ Características Principales

* 🔎 **Lectura Inteligente de PDFs:** Extrae datos esenciales de facturas ubicadas en carpetas específicas por empresa.
* 📊 **Extracción de Datos Clave:** Identifica información como cliente, NIF/CIF, número de factura, fechas, bases imponibles, IVA, total, y conceptos.
* ☁️ **Integración con Wintouch Cloud:** Envía los datos procesados directamente a la API REST de Wintouch.
* 🏢 **Soporte Multiempresa:** Permite configurar y gestionar múltiples empresas de forma independiente.
* 🧱 **Diseño Modular:** Facilita la extensión para procesar otros tipos de documentos o integrarse con otras plataformas.
* 🛡️ **Gestión de Errores:** Incluye mecanismos para manejar posibles errores durante la lectura del PDF o la comunicación con la API.

---

## 🗂️ Estructura del Proyecto

.
├── main.py                 # Script principal que orquesta todo el proceso.
├── config.py               # Configuración general (URLs API, parámetros globales).
├── lector_pdf.py           # Módulo encargado de leer y procesar los PDFs.
├── enviar_api.py           # Módulo para gestionar la comunicación con la API de Wintouch.
├── empresas/               # Directorio para configuraciones específicas por empresa.
│   └── empresaX.json       # Archivo de configuración para 'empresaX' (tokens, IDs, etc.).
│   └── empresaY.json       # Archivo de configuración para 'empresaY'.
├── pdfs/                   # Directorio donde se deben colocar los PDFs.
│   └── empresaX/           # PDFs para 'empresaX'.
│   │   └── factura1.pdf
│   └── empresaY/           # PDFs para 'empresaY'.
├── requirements.txt        # Listado de dependencias del proyecto.
└── .gitignore              # Especifica archivos/directorios a ignorar por Git (ej. claves API locales).


---

## 🔧 Tecnologías y Requisitos

* **Python 3.8+**
* **Bibliotecas Principales:**
    * `requests`: Para realizar las peticiones HTTP a la API.
    * `PyPDF2` o `pdfplumber`: Para la lectura y extracción de datos de archivos PDF. (Especifica cuál usas o si ambas son opciones).
    * (Cualquier otra biblioteca importante que utilices)

---

## 🚀 Instalación y Configuración

Sigue estos pasos para poner en marcha el proyecto:

1.  **Clonar el Repositorio:**
    ```bash
    git clone [https://github.com/tu-usuario/tu-repositorio.git](https://github.com/tu-usuario/tu-repositorio.git)
    cd tu-repositorio
    ```

2.  **Crear un Entorno Virtual (Recomendado):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # En Windows: venv\Scripts\activate
    ```

3.  **Instalar Dependencias:**
    Asegúrate de tener un archivo `requirements.txt` con todas las bibliotecas necesarias.
    ```bash
    pip install -r requirements.txt
    ```
    Si no tienes un `requirements.txt`, puedes crearlo con `pip freeze > requirements.txt` después de instalar las bibliotecas manualmente (`pip install requests PyPDF2 pdfplumber`).

4.  **Configurar Empresas:**
    * Dentro de la carpeta `empresas/`, crea un archivo JSON para cada empresa que quieras gestionar (ej. `miempresa.json`). Puedes usar `empresaX.json` como plantilla.
    * Rellena este archivo con los datos específicos de la empresa, como el token de la API de Wintouch, IDs necesarios, y cualquier otro parámetro de configuración.
        ```json
        // Ejemplo: empresas/miempresa.json
        {
          "api_token": "TU_API_TOKEN_AQUI",
          "id_cliente_wintouch": "ID_CLIENTE_ESPECIFICO",
          "otros_parametros": "valor"
        }
        ```

5.  **Preparar Carpetas de PDFs:**
    * Dentro de la carpeta `pdfs/`, crea una subcarpeta con el mismo nombre que usaste para el archivo JSON de configuración de la empresa (ej. `miempresa/`).
    * Coloca las facturas en formato PDF que quieras procesar dentro de esta carpeta.

---

## 🛠️ Uso

Una vez configurado, ejecuta el script principal desde la raíz del proyecto:

```bash
python main.py --empresa nombre_de_tu_empresa
Reemplaza nombre_de_tu_empresa con el nombre de la carpeta (y del archivo JSON de configuración sin la extensión) que has creado.

Por ejemplo, si tu archivo de configuración es empresas/clientealpha.json y tus PDFs están en pdfs/clientealpha/, el comando sería:

Bash

python main.py --empresa clientealpha
⚠️ Consideraciones Importantes
🔒 Seguridad de Credenciales: NUNCA subas claves de API, tokens o cualquier otra información sensible directamente al repositorio público. Utiliza variables de entorno o carga estos datos desde archivos locales que estén listados en tu .gitignore. Los archivos de configuración empresaX.json son un buen lugar si se mantienen locales y se listan en .gitignore, o se usan plantillas para ellos.
📂 Estructura de Carpetas: Es fundamental mantener la estructura de carpetas descrita (pdfs/nombre_empresa/, empresas/nombre_empresa.json) para el correcto funcionamiento del script.
➕ Añadir Nuevas Empresas: Para agregar una nueva empresa, simplemente crea su correspondiente archivo .json en la carpeta empresas/ y su subcarpeta en pdfs/.
👨‍💻 Autor
Stefan Mario Magura
GitHub: @StefanMarioMagura ```
