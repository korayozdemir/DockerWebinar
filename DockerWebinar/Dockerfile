#multistage
FROM mcr.microsoft.com/dotnet/core/sdk:3.1 as build
WORKDIR /app
COPY . .
RUN dotnet restore
RUN dotnet publish DockerWebinar.csproj -c Release -o test

FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
WORKDIR /app
COPY --from=build /app/test .

ENV ASPNETCORE_URLS="http://*:4600"
ENTRYPOINT ["dotnet","DockerWebinar.dll"]



#sdk

#FROM mcr.microsoft.com/dotnet/core/sdk:3.1
#WORKDIR /app
#COPY . .
#RUN dotnet restore
#RUN dotnet publish DockerWebinar.csproj -c Release -o test
#WORKDIR test
#ENV ASPNETCORE_URLS="http://*:4600"
#ENTRYPOINT ["dotnet","DockerWebinar.dll"]
#


#runtime

#FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
#WORKDIR /app
#COPY /bin/Release/netcoreapp3.1/publish .
#ENTRYPOINT ["dotnet","DockerWebinar.dll"]
#