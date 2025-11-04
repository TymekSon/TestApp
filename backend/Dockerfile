# backend/Dockerfile
FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /src

COPY MyApi/*.csproj ./MyApi/
RUN dotnet restore MyApi/MyApi.csproj

COPY MyApi/. ./MyApi/
WORKDIR /src/MyApi
RUN dotnet publish -c Release -o /app --no-restore

FROM mcr.microsoft.com/dotnet/aspnet:8.0 AS runtime
WORKDIR /app
COPY --from=build /app ./
ENTRYPOINT ["dotnet", "MyApi.dll"]