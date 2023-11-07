# Use the official image as a parent image
FROM mcr.microsoft.com/dotnet/aspnet:latest AS base
WORKDIR /app
EXPOSE 80

# Use the SDK image to build the app
FROM mcr.microsoft.com/dotnet/sdk:latest AS build
WORKDIR /src
COPY ["webserver.csproj", "./"]
RUN dotnet restore "webserver.csproj"
COPY . .
RUN dotnet build "webserver.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "webserver.csproj" -c Release -o /app/publish

# Generate runtime image
FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "webserver.dll"]
