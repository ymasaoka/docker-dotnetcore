
# docker-dotnetcore  
Provides docker-compose.yaml to launch a Docker container for .NET Core.  

# How to use  

1. **Clone this repository** to a directory of your choice.  
1. Move to the **docker-dotnetcore** directory.  
1. Execute the following command to start the container.  

    ```bash
    docker-compose up -d
    ```

1. Run the following command to confirm that the container has started.  

    ```bash
    docker-compose logs -f
    ```

## Creating .NET Core project  
Create a .NET Core project using the docker-compose command.  

```bash
docker-compose run --rm app dotnet new console -o <YourProjectName>
```

For `dotnet new` command options like *console*, check [here](https://docs.microsoft.com/en-us/dotnet/core/tools/dotnet-new) or use `--help` option to check it.  
You can also see other dotnet commands [here](https://docs.microsoft.com/en-us/dotnet/core/tools/).  

```bash
docker-compose run --rm app dotnet new --help
```

## Execute .NET Core Project  
The following command is an example of creating and executing a console application that displays `Hello World!` by using docker-compose command.  

```bash
docker-compose run --rm app dotnet new console -o MyFirstProject
docker-compose run -w /usr/src/MyFirstProject --rm app dotnet run
```

The `-w` option specifies the directory in which to run the command inside the container.  

# Related Repos
The repository specified by `image` in docker-compose.yaml can be changed depending on the usage.  
See the links below for more information.  

- .NET Core 2.1/3.1  
    - [dotnet/core/sdk](https://hub.docker.com/_/microsoft-dotnet-core-sdk/): .NET Core SDK  
    - [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/): ASP.NET Core Runtime  
    - [dotnet/core/runtime](https://hub.docker.com/_/microsoft-dotnet-core-runtime/): .NET Core Runtime  
    - [dotnet/core/runtime-deps](https://hub.docker.com/_/microsoft-dotnet-core-runtime-deps/): .NET Core Runtime Dependencies  
    - [dotnet/core/samples](https://hub.docker.com/_/microsoft-dotnet-core-samples/): .NET Core Samples  
- .NET 5.0+  
    - [dotnet/sdk](https://hub.docker.com/_/microsoft-dotnet-sdk/): .NET SDK  
    - [dotnet/aspnet](https://hub.docker.com/_/microsoft-dotnet-aspnet/): ASP.NET Core Runtime  
    - [dotnet/runtime](https://hub.docker.com/_/microsoft-dotnet-runtime/): .NET Runtime  
    - [dotnet/runtime-deps](https://hub.docker.com/_/microsoft-dotnet-runtime-deps/): .NET Runtime Dependencies  