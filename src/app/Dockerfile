# base
FROM microsoft/dotnet:1.1.1-sdk

# set up network (doesn't work on heroku) 
EXPOSE 5000/tcp

ENV DOTNET_USE_POLLING_FILE_WATCHER=1
ENV ASPNETCORE_URLS http://*:5000

WORKDIR /var/www/app

ENTRYPOINT ["/bin/bash", "-c"]

# Build and run the app if present, with watcher, when the container spins up
CMD ["dotnet restore && dotnet watch run"]