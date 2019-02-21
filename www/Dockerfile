FROM microsoft/dotnet:2.2-aspnetcore-runtime
WORKDIR /app
EXPOSE 80
EXPOSE 443

COPY ./www .
ENTRYPOINT ["dotnet", "www.dll"]
