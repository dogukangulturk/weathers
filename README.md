# Open Weather Service Application


### The service provides an API
#### `WeatherAPI`
* To search current weather report by city name.


### How does the application works?
* Application receives the requested via `/v1/api/open-weather/{city}` url with `{city}` path variables
* There is a validation for city parameter. City value can not be decimal or a blank value. 
  * If the city value is not valid, api returns `400 - Http Bad Request` response
* Current weather report can be fetch either from database or WeatherStackAPI with the API_KEY
  * If the latest data is not older than 30 minutes for that city value, data is fetching from db.
  * Either city does not exist or older than 30 minutes in DB, a request sends to WeatherStackAPI and the result puts to Cache
  * If there is a value with city filter as key in cache, the response is returns from cache directly

On the swagger page you can find the relevant api endpoint. 
You can reach the openapi page by `http://localhost:8080/swagger-ui/index.html` url.

You can define <b>WEATHER_STACK_API_KEY </b> in the `.env` file

## Technologies

---
- Java 17
- Spring Boot 3.0
- Open API Documentation
- Spring Data JPA
- Kotlin
- H2 In Memory Database
- Restful API
- Maven
- Docker
- Docker Compose
- Prometheus
- Grafana
