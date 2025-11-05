# Hello World API

A simple Flask-based REST API that serves a welcoming JSON message. This project demonstrates a basic microservice architecture with containerization, automated testing, and continuous integration/deployment.

## Features

- **Single Endpoint**: Provides a `/` route that returns a JSON response with a hello message.
- **Flask Framework**: Built using Flask for lightweight web development.
- **Docker Support**: Fully containerized for easy deployment and portability.
- **Unit Testing**: Includes pytest-based tests to ensure reliability.
- **CI/CD Pipeline**: Automated GitHub Actions workflow for building, testing, linting, and deploying to Docker Hub.
- **Security Scanning**: Integrated Trivy for vulnerability scanning of Docker images.

## Installation

### Prerequisites
- Python 3.12 or higher
- Docker (for containerized deployment)
- Git

### Local Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/hello-world-api.git
   cd hello-world-api
   ```

2. Create a virtual environment and install dependencies:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   pip install -r requirements.txt
   ```

3. Run the application:
   ```bash
   python app/main.py
   ```

The API will be available at `http://localhost:5000`.

### Docker Setup
1. Build the Docker image:
   ```bash
   docker build -t hello-world-api .
   ```

2. Run the container:
   ```bash
   docker run -p 5000:5000 hello-world-api
   ```

## Usage

### API Endpoint
- **GET /**: Returns a JSON message.
  - Response: `{"message": "Hello, PeopleHum!"}`

### Example Request
```bash
curl http://localhost:5000/
```

## Testing

Run the unit tests using pytest:
```bash
pytest tests/
```

For linting:
```bash
flake8 app tests
```

## Deployment

The project includes a GitHub Actions CI/CD pipeline that:
- Lints the code with flake8
- Runs unit tests
- Builds a Docker image
- Pushes the image to Docker Hub (`shegezzy/hello-world-api`)
- Performs security scanning with Trivy

To deploy:
1. Push changes to the `main` branch.
2. The pipeline will automatically build and deploy the image.

### Manual Docker Deployment
```bash
docker build -t your-registry/hello-world-api .
docker push your-registry/hello-world-api
```

## Contributing

1. Fork the repository.
2. Create a feature branch: `git checkout -b feature/your-feature`.
3. Make your changes and add tests.
4. Run tests: `pytest tests/`.
5. Commit your changes: `git commit -am 'Add new feature'`.
6. Push to the branch: `git push origin feature/your-feature`.
7. Submit a pull request.


