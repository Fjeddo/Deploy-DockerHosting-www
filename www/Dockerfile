FROM microsoft/dotnet:2.2-aspnetcore-runtime AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM microsoft/dotnet:2.2-sdk AS build
WORKDIR /src
COPY ["www/www.csproj", "www/"]
RUN dotnet restore "www/www.csproj"
COPY . .
WORKDIR "/src/www"
RUN dotnet build "www.csproj" -c Release -o /app

FROM build AS publish
RUN dotnet publish "www.csproj" -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "www.dll"]