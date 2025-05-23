# Proyecto 3: Automatización de Facturas para Wintouch 🧾🤖

Este proyecto automatiza la extracción de datos de facturas en formato PDF y su envío a la plataforma Wintouch Cloud a través de su API REST.  
Está pensado para facilitar la gestión documental y administrativa de empresas, eliminando procesos manuales y mejorando la eficiencia.

---
🔍 Descripción

- Se procesa un PDF con facturas ubicado en la carpeta de la empresa correspondiente.
- Se extraen los datos clave (cliente, importe, fecha, conceptos, etc.).
- Se genera y envía una petición POST a la API de Wintouch con esos datos para registrar la factura.
- El proyecto está modularizado en varios archivos para facilitar mantenimiento y escalabilidad.

---

 🚀 Cómo ejecutar

Para ejecutar el proyecto, abre una terminal en la raíz del repositorio y lanza:

```bash
python main.py --empresa empresa1
La opción --empresa indica la carpeta y configuración que se utilizará (por ejemplo empresa1).

Se lee el PDF en pdfs/empresa1/.

Se toma la configuración desde empresas/empresa1.json.

Se procesa la factura y se envía a la API.

📁 Archivos del repositorio
main.py: Controla el flujo completo, llamando a la función que lee el PDF, procesa los datos y llama al módulo para enviar la petición a Wintouch.

config.py: Define variables globales como la URL base de la API de Wintouch para fácil mantenimiento.

enviar_api.py: Contiene funciones que generan y envían las peticiones HTTP hacia la API, gestionando respuestas y errores.

lector_pdf.py: Encargado de abrir el PDF, extraer los datos necesarios y devolverlos en formato estructurado para su envío.

empresas/empresa1.json: Archivo JSON con datos específicos para la empresa, como EnterpriseID, DocumentTypeID, EntityID, y claves API (no subir datos reales en repositorios públicos).

pdfs/empresa1/: Carpeta donde se almacenan los PDFs a procesar por empresa.

README.md: Este archivo de documentación.

🧠 Tecnologías utilizadas
Python 🐍

Librerías para procesamiento PDF (PyPDF2, pdfplumber, etc.)

Requests para consumo de API REST

JSON para manejo de configuraciones

📌 Notas
Nunca subir claves API reales a repositorios públicos. Usa .gitignore para evitar que archivos con credenciales se suban.

La estructura de las carpetas debe mantenerse para que el programa funcione correctamente.

Puedes añadir más configuraciones para otras empresas creando más archivos JSON dentro de empresas/ y carpetas correspondientes en pdfs/.

El proyecto está preparado para ser escalable y adaptable a otros tipos de documentos.

📬 Autor
Stefan Mario Magura – GitHub


