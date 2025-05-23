# Proyecto 3: Automatización de Facturas para Wintouch 🧾🤖

Este proyecto automatiza la extracción de datos de facturas en PDF y su envío a la plataforma Wintouch Cloud vía API REST.  
Facilita la gestión documental y administrativa, eliminando procesos manuales y mejorando la eficiencia.

---

## 🔍 Descripción

- Procesa PDFs de facturas ubicados en carpetas específicas por empresa.
- Extrae datos clave: cliente, importe, fecha, conceptos, etc.
- Genera y envía peticiones POST a la API de Wintouch para registrar facturas.
- Modular y escalable, preparado para múltiples empresas y tipos de documentos.

---

## 🚀 Cómo ejecutar

Abre una terminal en la raíz del repositorio y ejecuta:

```bash
python main.py --empresa empresa1
Donde:

--empresa empresa1: Indica la configuración y carpeta de la empresa a usar.

Se lee el PDF en pdfs/empresa1/.

La configuración se toma desde empresas/empresa1.json.

La factura se procesa y envía automáticamente a la API.

📁 Archivos clave
Archivo	Descripción
main.py	Controla el flujo principal: lee PDF, procesa datos y envía la petición a Wintouch.
config.py	Variables globales como URL base de la API para fácil mantenimiento.
enviar_api.py	Funciones que crean y envían peticiones HTTP, gestionando respuestas y errores.
lector_pdf.py	Extrae datos estructurados de facturas a partir de PDFs.
empresas/empresa1.json	Configuración específica por empresa (EnterpriseID, DocumentTypeID, EntityID, API Keys).
pdfs/empresa1/	Carpeta donde se almacenan los PDFs a procesar para cada empresa.
README.md	Documentación del proyecto.

🧠 Tecnologías usadas
Python 🐍

Librerías para procesamiento de PDFs (PyPDF2, pdfplumber, etc.)

Requests para consumo de API REST

JSON para configuraciones

⚠️ Notas importantes
Nunca subir claves API reales a repositorios públicos. Usa .gitignore para evitarlo.

Mantén la estructura de carpetas para que el programa funcione correctamente.

Para añadir empresas, crea archivos JSON nuevos en empresas/ y carpetas de PDFs en pdfs/.

El proyecto está pensado para ser escalable y adaptable a distintos documentos y clientes.

📬 Autor
Stefan Mario Magura – GitHub

