# DockerComposeMSADemo
## A Microservice Application deployed to a Docker Compose group on an Azure VM.

## DemoApp
An Angular single page application, designed to send HTTP GET requests to the  jsonplaceholder.typicode.com to-do API, and the HelloApp API. Returned information is displayed for the user.

## HelloApp
A .NET minimal API in C#, designed to return on several endpoints:
- {url}/weatherforecast - returns a set of 5 random weather forecasts
- {url}/count - returns a running request count
- {url}/time - returns the current system time of the API service
- {url}/ - returns the string "Hello there! I'm alive!"

## Docker Containers
Both services include a Dockerfile for containerization, and a docker-compose.yml is stored in the root directory of the repository.
