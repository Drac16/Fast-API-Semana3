Mi Primera API FastAPI - Bootcamp
��� Desarrollador: Angel Rodriguez ��� Email: 200131428+Drac16@users.noreply.github.com � Privacidad: Email configurado según mejores prácticas de GitHub ���� Fecha de creación: 2025-08-15 23:04:20 ��� Ruta del proyecto: /c/Users/python/desarrollo-personal/angel-rodriguez-bootcamp/mi-primera-api-fastapi ��� Equipo de trabajo: DESKTOP-DOG67T6

��� Configuración Local
Este proyecto está configurado para trabajo en equipo compartido:

Entorno virtual aislado: venv-personal/
Configuración Git local: Solo para este proyecto
Dependencias independientes: No afecta otras instalaciones
��� Instalación y Ejecución
# 1. Activar entorno virtual personal
source venv-personal/bin/activate

# 2. Instalar dependencias (si es necesario)
pip install -r requirements.txt

# 3. Ejecutar servidor de desarrollo
uvicorn main:app --reload --port 8000
��� Notas del Desarrollador
Configuración Git: Local únicamente, no afecta configuración global
Email de GitHub: Configurado con email privado para proteger información personal
Entorno aislado: Todas las dependencias en venv-personal/
Puerto por defecto: 8000 (cambiar si hay conflictos)
Estado del bootcamp: Semana 1 - Configuración inicial
���️ Troubleshooting Personal
Si el entorno virtual no se activa: rm -rf venv-personal && python3 -m venv venv-personal
Si hay conflictos de puerto: cambiar --port en uvicorn
Si Git no funciona: verificar git config user.name y git config user.email
Si necesitas cambiar el email: usar el email privado de GitHub desde Settings → Emails
Mi API FastAPI - Semana 2
¿Qué hace?
API mejorada con validación automática de datos y type hints.

Nuevos Features (Semana 2)
✅ Type hints en todas las funciones
✅ Validación automática con Pydantic
✅ Endpoint POST para crear datos
✅ Parámetros de ruta (ejemplo: /products/{id})
✅ Búsqueda con parámetros query
¿Cómo ejecutar?
pip install fastapi pydantic uvicorn
uvicorn main:app --reload
REFLEXION Este trabajo me ayudó a entender cómo configurar entornos virtuales y usar herramientas como FastAPI para el desarrollo Además, me recordó que cada paso aprendido fortalece mis bases como desarrollador

API de Productos con FastAPI
Esta es una API REST desarrollada con FastAPI, organizada con una estructura modular y profesional.
Permite gestionar productos (crear, listar, actualizar, eliminar y buscar) con respuestas consistentes y manejo de errores personalizados.

Requisitos
Python 3.9+
pip o pipenv (gestor de dependencias)
FastAPI y Uvicorn
Instalación
Clonar el repositorio o copiar el proyecto:

git clone https://github.com/tu-usuario/tu-repo.git
cd tu-repo/app
Crear y activar un entorno virtual (opcional pero recomendado):

bash Copiar código python -m venv venv source venv/bin/activate # Linux/Mac venv\Scripts\activate # Windows Instalar dependencias:

bash Copiar código pip install fastapi uvicorn Ejecución Ejecuta el servidor con:

bash Copiar código uvicorn main:app --reload El parámetro --reload recarga automáticamente el servidor cuando modificas código.

Documentación interactiva: -> http://127.0.0.1:8000/docs (Swagger UI) -> http://127.0.0.1:8000/redoc (ReDoc)

Estructura del Proyecto bash Copiar código app/ ├── main.py # Punto de entrada de la API ├── models/ # Modelos de datos con Pydantic │ └── product_models.py ├── data/ # Datos simulados (mock) │ └── products_data.py ├── routers/ # Rutas separadas (ejemplo: products) │ └── products.py ├── utils.py # Funciones auxiliares (respuestas uniformes) └── exceptions.py # Excepciones personalizadas Endpoints Principales Health Check http Copiar código GET /health Respuesta:

json Copiar código { "success": true, "message": "API funcionando correctamente", "data": {}, "timestamp": "2025-08-27T14:00:00" } Listar Productos http Copiar código GET /products?skip=0&limit=5&min_price=10&max_price=100 Buscar Productos http Copiar código GET /products/search?name=camisa&min_price=20&max_price=200 Crear Producto http Copiar código POST /products Body (JSON):

json Copiar código { "name": "Zapatos deportivos", "description": "Zapatos de running cómodos", "price": 120.5 } Actualizar Producto http Copiar código PUT /products/1 Body (JSON):

json Copiar código { "name": "Camisa actualizada", "description": "Camisa de algodón premium", "price": 45.0 } Eliminar Producto http Copiar código DELETE /products/1 Manejo de Errores La API devuelve errores consistentes con este formato:

json Copiar código { "success": false, "error": { "message": "Producto no encontrado", "status_code": 404, "timestamp": "2025-08-27T14:05:00", "details": { "requested_id": 99 } } } 📜 Licencia Este proyecto es de uso libre para fines educativos y de práctica con FastAPI.