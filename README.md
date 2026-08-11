# gestor-gastos

# 🧾 Gestor de Gastos Colaborativo v1.0

## 📌 Descripción del Proyecto
Sistema backend para equipos remotos que permite registrar gastos empresariales mediante:
- API REST con FastAPI.
- Lectura automática de tickets/facturas mediante OCR (Tesseract).
- Notificaciones y creación de gastos vía WhatsApp (Twilio API).
- Almacenamiento de imágenes en la nube (S3/Azure Blob).

**Objetivo:** Demostrar competencias en arquitectura por capas, integración de servicios externos y automatización de procesos.

---

## 🗓️ Planificación y Seguimiento de Horas

> **Metodología:** Cada fase se estima en horas netas de programación (sin contar pausas).  
> **Jornada media estimada:** 3-4 horas al día (para ser realistas con un junior que no programa 8h diarias).

| Fase | Tarea | Horas Estimadas | Horas Reales | Fecha Inicio | Fecha Fin | Estado |
|------|-------|----------------|--------------|--------------|-----------|--------|
| **Fase 0** | Configuración inicial (entorno, GitHub, .env, requirements) | 2h | | | | ⬜ Pendiente |
| **Fase 1** | API básica: CRUD de gastos (sin autenticación) con SQLite | 6h | | | | ⬜ Pendiente |
| **Fase 2** | Autenticación JWT (registro, login, protección de rutas) | 5h | | | | ⬜ Pendiente |
| **Fase 3** | Conexión a PostgreSQL (cambiar SQLite → PostgreSQL con Docker) | 4h | | | | ⬜ Pendiente |
| **Fase 4** | Servicio de OCR (subir imagen → extraer monto y fecha con Tesseract) | 6h | | | | ⬜ Pendiente |
| **Fase 5** | Subida de archivos a la nube (Azure Blob o S3) | 5h | | | | ⬜ Pendiente |
| **Fase 6** | Integración con WhatsApp (Twilio) - Modo recepción de mensajes | 5h | | | | ⬜ Pendiente |
| **Fase 7** | Servicio de Background Jobs (enviar resumen diario por email) | 4h | | | | ⬜ Pendiente |
| **Fase 8** | Tests unitarios (pytest) - mínimo 10 tests | 4h | | | | ⬜ Pendiente |
| **Fase 9** | Dockerizar el proyecto (Dockerfile + docker-compose) | 3h | | | | ⬜ Pendiente |
| **Fase 10** | Documentación final y limpieza de código | 2h | | | | ⬜ Pendiente |
| | **TOTAL ESTIMADO** | **46h** | | | | |

---

## 📊 Progreso Real
- **Horas invertidas hasta hoy:** 0h
- **Porcentaje completado:** 0%
- **Próxima tarea:** Fase 0 - Configuración inicial

---

## 🛠️ Tecnologías utilizadas
- **Lenguaje:** Python 3.11+
- **Framework:** FastAPI
- **ORM:** SQLAlchemy (con Alembic para migraciones)
- **BD:** PostgreSQL (desarrollo en SQLite)
- **OCR:** Tesseract + Pillow
- **Mensajería:** Twilio API (WhatsApp)
- **Tareas asíncronas:** Celery + Redis (o APScheduler para versión simplificada)
- **Contenedores:** Docker & Docker Compose
- **Cloud:** Azure Blob Storage (o AWS S3)
- **Tests:** pytest

---

## 🚀 Cómo levantar el proyecto (para recruiters)

# 1. Clonar repositorio
git clone https://github.com/tu_usuario/gestor-gastos.git

# 2. Crear entorno virtual
python -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate

# 3. Instalar dependencias
pip install -r requirements.txt

# 4. Configurar variables de entorno (copiar .env.example a .env)

# 5. Ejecutar migraciones de BD
alembic upgrade head

# 6. Levantar el servidor
uvicorn main:app --reload

---

## 📝 Notas personales (para mí)

- *[Espacio para apuntar problemas encontrados y soluciones]*
- *Ej: "El OCR fallaba con imágenes oscuras, añadí preprocesado con OpenCV"*
- *Ej: "Twilio solo admite mensajes en formato específico, tuve que parsear el texto"*
- *Ej: "La migración de SQLite a PostgreSQL dio error por las mayúsculas en los nombres de las tablas"*

---

## 📎 Enlaces de interés

- [Documentación de FastAPI](https://fastapi.tiangolo.com/)
- [Guía de Twilio para WhatsApp](https://www.twilio.com/docs/whatsapp)
- [Tutorial de Docker para principiantes](https://docs.docker.com/get-started/)
- [SQLAlchemy ORM - Guía rápida](https://docs.sqlalchemy.org/en/20/orm/quickstart.html)
- [Pytest - Documentación oficial](https://docs.pytest.org/en/stable/)
- [Tesseract OCR - Configuración en Python](https://pypi.org/project/pytesseract/)

---


## 🐛 Errores conocidos / TODO

- [ ] El OCR no reconoce tickets con fuentes muy pequeñas (pendiente de probar con OpenCV).
- [ ] Los mensajes de WhatsApp con tildes se codifican mal, hay que aplicar `unidecode`.
- [ ] Mejorar la paginación en el endpoint GET /api/gastos (actualmente devuelve todos).
- [ ] Añadir logging con colores para facilitar la depuración.

---

## 🧑‍💻 Autor

**Luis Jiménez Ruiz**  
- [LinkedIn](https://www.linkedin.com/in/betadotdev/)  
- [Portfolio](https://tu-portfolio.com)  
- [GitHub](https://github.com/BetaDotDev)

---

## 📜 Licencia

Este proyecto es de código abierto y está disponible bajo la licencia [MIT](https://opensource.org/licenses/MIT).
