# Imagen base específica
FROM python:3.11-slim

# Crear usuario no-root
RUN useradd -m appuser

# Directorio de trabajo
WORKDIR /app

# Copiar e instalar dependencias primero
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copiar código de la aplicación
COPY app.py .

# Variable de entorno y puerto
ENV PORT=5000
EXPOSE 5000

# Cambiar a usuario no-root
USER appuser

# Comando por defecto
CMD ["python", "app.py"]
