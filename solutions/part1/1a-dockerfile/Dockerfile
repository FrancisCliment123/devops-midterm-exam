FROM python:3.13
WORKDIR /app

# FIX: Do not pass the API key natively in the Dockerfile (Hardcoded Secret)
# Removed: ENV API_KEY=sk-secret-key-do-not-share

COPY . .

# FIX: Used 'uv' for package management and install the project from pyproject.toml
RUN pip install uv && uv pip install --system .

# FIX: Changed EXPOSE from 8000 to 8080 to match the architecture diagram requirements
EXPOSE 8080

# FIX: The app is installed as a package, so we use the console script entry point instead of python src/main.py
CMD ["mock-openai-api"]
