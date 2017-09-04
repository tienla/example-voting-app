FROM microsoft/dotnet:1.1.1-sdk

WORKDIR /code

ADD /worker/src/Worker /worker/code/src/Worker

RUN dotnet restore -v minimal /worker/src/Worker \
    && dotnet publish -c Release -o "./" "/worker/src/Worker/" 

CMD dotnet /worker/src/Worker/Worker.dll