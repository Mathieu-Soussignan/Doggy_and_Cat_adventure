# Base image
FROM python:3.9-slim

# Set working directory
WORKDIR /app

# Copy dependencies
COPY requirements.txt .

# Install only what's necessary for the API
RUN pip install --no-cache-dir fastapi uvicorn[standard] python-multipart \
    && pip install --no-cache-dir -r requirements.txt

# Copy project files
COPY ./api ./api
COPY ./src ./src
COPY ./config ./config

# Expose the API port
EXPOSE 8000

# Launch the FastAPI app
CMD ["uvicorn", "api.main:app", "--host", "0.0.0.0", "--port", "8000"]