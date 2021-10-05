# steeltoe-service-discovery-demo

A simple example of the steeltoe service discovery based on the tutorial: https://steeltoe.io/service-discovery/get-started/eureka

Run the Eureka Docker container:
```powershell
docker run --publish 8761:8761 steeltoeoss/eureka-server
```

View the Eureka Dashboard: http://localhost:8761/
Notice no applications are registered yet.

Start Microservice A:
```powershell
dotnet run --project .\MicroserviceA\MicroserviceA.csproj
```

Start Microservice A:
```powershell
dotnet run --project .\MicroserviceB\MicroserviceB.csproj
```

Refresh Eureka Dashboard to show Microservice A and B are now registered.

Call microservice endpoints:
- Microservice A: https://localhost:5003/api/values
- Microservice B: https://localhost:5001/weatherforecast
