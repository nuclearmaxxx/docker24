FROM mcr.microsoft.com/dotnet/sdk:6.0-jammy as build
WORKDIR /work
COPY . /work
RUN ["dotnet","build","WebApplication_DIT_Docker.sln"]

FROM mcr.microsoft.com/dotnet/aspnet:6.0-jammy
WORKDIR /apps
COPY --from=build /work/WebApplication_DIT_Docker/bin/Debug/net6.0/* /apps
EXPOSE 5000
ENTRYPOINT ["dotnet","WebApplication_DIT_Docker.dll"]

