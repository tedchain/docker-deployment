FROM microsoft/dotnet:1.1-sdk-projectjson

RUN mkdir -p /tmp/tedchain \
    && mkdir -p /tedchain

COPY project.json /tmp/tedchain/project.json
COPY Program.cs /tmp/tedchain/Program.cs

RUN cd /tmp/tedchain \
    && dotnet restore \
    && dotnet publish -o /tedchain

WORKDIR /tedchain

EXPOSE 8080
ENTRYPOINT ["dotnet", "tedchain.dll"]
