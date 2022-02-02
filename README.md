# Introduction
This guide provides the details about the solution and instructions to run this project in your machine.

# Requirements
- This project is created in .Net 6. To run this project locally, you need Visual studio 2022 in your machine.
- Serliog file logger is used to log the errors and therefore it requires permission to create a folder named **Logs** and create and write **.txt** files.

> [!WARNING]
> This project uses `Microsoft.VisualStudio.Azure.Containers.Tools.Targets`. So, if your machine does not have docker desktop, then you may get a warning like [mentioned here](https://developercommunity.visualstudio.com/t/visual-studio-2019-package-did-not-load-correctly/1408219).

# Swagger
Swagger UI is included in this project.

# Steps
- Dowload this project from the Github.
- Unzip the files and open the solution file, CalculatePowerGenerationByPowerPlants.sln using VS 2022.
- Build the solution to restore the nuget packages.
- Run the project using kestrel/IIS express and you should be able to view the swagger UI.(http://localhost:8888/swagger/index.html)

# Endpoint
The endpoint for this code challenge is http://localhost:8888/api/v1/productionplan, which is a POST method.

# Docker
This project is also provided with Dockerfile. If your machine has Docker Desktop installed, this is another option to run the solution in a container. The default target OS is set to Linux.

# Requirements
- Need to have Docker Desktop installed with Linux container


# Steps to run app in a container
- Dowload this project from the Github.
- Unzip the files and go to the folder of the solution file, CalculatePowerGenerationByPowerPlants.sln.
- Open Command Propmt in this folder.
- Run the command `docker build -t nameoftheimage:tag -f src\CalculatePowerGenerationByPowerPlants\Dockerfile .`
- After the image is built successfully, run the command `docker run -d -p 8888:80 -e ASPNETCORE_URLS="http://+:80" -e ASPNETCORE_ENVIRONMENT="Development"  nameoftheimage:tag`.
- Once the command is executed successfully, Swagger UI can be accessed via http://localhost:8888/swagger/index.html and the endpoint should be accessible via http://localhost:8888/api/v1/productionplan. 