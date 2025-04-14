FROM python:3.9-slim

WORKDIR /app

# Copy requirements first for better caching
COPY requirements.txt /app/
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application
COPY . /app/

# Set environment variables for Flask
ENV FLASK_APP=app
ENV FLASK_ENV=development

# Expose the port that Flask runs on
EXPOSE 5001

# Use entrypoint to allow passing commands
ENTRYPOINT ["flask"]
CMD ["run", "--host=0.0.0.0", "--port=5001"]