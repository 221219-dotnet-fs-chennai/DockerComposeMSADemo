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

## Manual Testing
Begin by verifying that the services will run independantly in a local environment.
- use `dotnet run` to run HelloApp
- once started, use a browser or HTTP messaging tool (like Postman or ThunderClient) to send GET requests to the HelloApp on `https://localhost:7069` to verify its functionality.

- use `npm run start` to run DemoApp
- use a browser to navigate to the running application (port 4200 by default), and use the "Display Posts" button to send a request to the jsonplaceholder.typicode.com API. You should see a list of bullet points displayed as a result of the request and response.

Once independant functionality is verified interaction can be verified. Becuase the .NET SDK and runtime will assign ports to an application at the time of project creation, ports can be modified and edited in launchSettings.json. For this demo, the ports are fixed and should be consistent throughout the examples provided.

- use a browser to navigate to the running application (port 4200 by default), and use the "Display Time" button to send a request to the HelloApp service. You should see the current system time of the API displayed as a result of the request and response. You should also see the "Current count is:" message now also displays a value.
- use a browser or HTTP messaging tool (like Postman or ThunderClient) to send GET requests to the HelloApp on `https://localhost:7069/count`. The response from the HellApp should be a value greater than the result last displayed on the DemoApp page.
