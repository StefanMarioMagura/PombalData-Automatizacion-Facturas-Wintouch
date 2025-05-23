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
