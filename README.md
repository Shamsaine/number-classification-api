# Number Classification API

The **Number Classification API** is a Spring Boot application that takes a number as input and returns its properties, such as whether it is prime, perfect, Armstrong, even/odd, and its digit sum. Additionally, it fetches a fun fact about the number using the [Numbers API](http://numbersapi.com).

## Features

- Classifies a number as:
  - Prime
  - Perfect
  - Armstrong
  - Even or Odd
- Calculates the digit sum of the number.
- Fetches a fun fact about the number from an external API.
- Provides a RESTful API endpoint for easy integration.

## API Endpoint

### Classify Number

**URL:** `/api/classify-number`

**Method:** `GET`

**Query Parameter:**
- `number` (required): The number to classify.

**Response:**
- On success:
  ```json
  {
    "number": 28,
    "isPrime": false,
    "isPerfect": true,
    "isArmstrong": false,
    "isEven": true,
    "digitSum": 10,
    "funFact": "28 is a perfect number.",
    "properties": ["even", "perfect"]
  }
  ```
- On error (e.g., invalid input):
  ```json
  {
    "error": true,
    "number": "invalid_input"
  }
  ```

## How to Run

### Prerequisites
- Java 17 or higher
- Maven
- Docker (optional, for containerization)

### Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/number-classification-api.git
   cd number-classification-api
   ```

2. Build the project:
   ```bash
   mvn clean install
   ```

3. Run the application:
   ```bash
   mvn spring-boot:run
   ```

4. Access the API at `http://localhost:8080/api/classify-number`.

### Running with Docker
1. Build the Docker image:
   ```bash
   docker build -t number-classification-api .
   ```

2. Run the container:
   ```bash
   docker run -p 8080:8080 number-classification-api
   ```

3. Access the API at `http://localhost:8080/api/classify-number`.

## Project Structure

- **`NumberService`**: Contains the logic for classifying numbers and fetching fun facts.
- **`NumberController`**: Exposes the REST API endpoint.
- **`NumberResponse`**: Defines the structure of the API response.
- **`NumbersClassifierApplication`**: The main entry point of the Spring Boot application.

## Example Usage

To classify the number `28`, send a GET request to:
```
http://localhost:8080/api/classify-number?number=28
```

Response:
```json
{
  "number": 28,
  "isPrime": false,
  "isPerfect": true,
  "isArmstrong": false,
  "isEven": true,
  "digitSum": 10,
  "funFact": "28 is a perfect number.",
  "properties": ["even", "perfect"]
}
```

## Technologies Used

- **Java**: Programming language.
- **Spring Boot**: Framework for building the API.
- **Maven**: Build tool.
- **Numbers API**: External API for fetching fun facts.
- **Docker**: For containerization.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Author

- **Your Name**  
  GitHub: [shamsaine](https://github.com/shamsaine)

## Acknowledgments

- [Numbers API](http://numbersapi.com) for providing fun facts about numbers.
