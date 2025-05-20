# Base image
FROM python:3.9-slim

# Set working directory
WORKDIR /app

# Copy requirements
COPY requirements.txt .

# Install minimal dependencies
RUN pip install --no-cache-dir streamlit \
    && pip install --no-cache-dir -r requirements.txt

# Copy app files
COPY ./streamlit_app ./streamlit_app
COPY ./src ./src
COPY ./config ./config

# Expose default Streamlit port
EXPOSE 8501

# Run the app
CMD ["streamlit", "run", "streamlit_app/app.py", "--server.port=8501", "--server.address=0.0.0.0"]