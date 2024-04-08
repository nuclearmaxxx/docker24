FROM mcr.microsoft.com/dotnet/sdk:6.0-jammy as build
WORKDIR /work
COPY . /work
RUN dotnet restore ./WebApplication_DIT_Docker/WebApplication_DIT_Docker.csproj \
	&& dotnet build ./WebApplication_DIT_Docker/WebApplication_DIT_Docker.csproj --no-restore --configuration Release \
	&& dotnet publish ./WebApplication_DIT_Docker/WebApplication_DIT_Docker.csproj --no-build --configuration Release -o /work/publish

FROM mcr.microsoft.com/dotnet/aspnet:6.0-jammy
WORKDIR /apps
COPY --from=build /work/publish/* /apps
EXPOSE 80
ENTRYPOINT ["dotnet","WebApplication_DIT_Docker.dll"]

