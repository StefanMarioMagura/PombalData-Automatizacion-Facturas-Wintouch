# 📂 Proyecto Automatización Facturas Wintouch

Automatiza la lectura de facturas en PDF y el envío de datos a la plataforma Wintouch Cloud mediante su API REST. Ideal para gestionar facturación de forma rápida y sin errores manuales.

---

## ⚙️ ¿Qué hace este proyecto?

- Lee PDFs con facturas en carpetas específicas por empresa.  
- Extrae los datos esenciales (cliente, importe, fecha, conceptos).  
- Envía esos datos a Wintouch usando peticiones HTTP.  
- Soporta múltiples empresas con configuraciones independientes.  
- Modular y extensible para otros tipos de documentos.

---

## 🚀 Instrucciones de uso

1. Clona o descarga este repositorio.  
2. Coloca tus PDFs en la carpeta `pdfs/empresaX/` (crea la carpeta con el nombre de tu empresa).  
3. Configura los parámetros de la empresa en `empresas/empresaX.json`.  
4. Ejecuta el siguiente comando, cambiando `empresaX` por el nombre de tu empresa:

```bash
python main.py --empresa empresaX

---

## 🗂 Estructura principal de archivos
Archivo / Carpeta	Función principal
main.py	Orquesta el proceso completo: lee PDF y envía datos a Wintouch
config.py	Variables globales, URLs y configuraciones generales
lector_pdf.py	Extrae y procesa datos de los PDFs
enviar_api.py	Gestiona las peticiones HTTP hacia la API y sus respuestas
empresas/empresaX.json	Datos específicos de la empresa (IDs, API keys, etc.)
pdfs/empresaX/	Lugar donde se guardan los PDFs para cada empresa

## 🔧 Requisitos y tecnologías
Python 3.x

Librerías: PyPDF2 o pdfplumber para PDFs

requests para comunicaciones HTTP

Archivos JSON para configuraciones

Puedes instalar las dependencias con:

bash
Copiar
Editar
pip install -r requirements.txt

---

## ⚠️ Consideraciones importantes
No subir datos sensibles: nunca publiques claves API o credenciales reales en repositorios públicos. Usa .gitignore.

Mantén la estructura de carpetas para que el código funcione correctamente.

Para añadir nuevas empresas, crea sus carpetas y archivos JSON de configuración.

👨‍💻 Autor
Stefan Mario Magura – GitHub
