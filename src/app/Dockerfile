# base
FROM microsoft/dotnet:1.1.1-sdk

# set up package cache
# RUN curl -o /tmp/packagescache.tar.gz http://dist.asp.net/packagecache/1.1.1/debian.8-x64/aspnetcore.cache.tar.gz && \
#     mkdir /packagescache && cd /packagescache && \
#     tar xvf /tmp/packagescache.tar.gz && \
#     rm /tmp/packagescache.tar.gz && \
#     cd /
 
# # set env var for packages cache
# ENV DOTNET_HOSTING_OPTIMIZATION_CACHE /packagescache

# set up network (doesn't work on heroku) 
EXPOSE 5000/tcp

ENV DOTNET_USE_POLLING_FILE_WATCHER=1
ENV ASPNETCORE_URLS http://*:5000

# # copy my app from current directory 
#COPY . /app 
WORKDIR /var/www/app

# # Build and run the app if present, with watcher, when the container spins up
#RUN ["dotnet", "restore"]
#RUN ["dotnet", "build"]
CMD ["/bin/bash", "-c", "dotnet restore && dotnet watch run"]