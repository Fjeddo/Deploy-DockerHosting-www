FROM microsoft/dotnet:2.2-aspnetcore-runtime
WORKDIR /app
EXPOSE 80
EXPOSE 443

COPY /app .
ENTRYPOINT ["dotnet", "www.dll"]
