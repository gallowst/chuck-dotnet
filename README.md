# Chuck Norris - Dot Net Sample Application

[![Build Status](https://dev.azure.com/gallowst/docker/_apis/build/status%2Fgallowst.chuck-dotnet?branchName=main)](https://dev.azure.com/gallowst/docker/_build/latest?definitionId=33&branchName=main)

This repository provides a sample .Net 6.0 ASP application implemented using the Dot Net web framework. It is intended to be used to demonstrate deployment of .Net 6.0 WebApps to Azure.

## Implementation Notes

### Dotnet install

- On Debian

~~~bash
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
rm packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install -y dotnet-sdk-7.0
~~~

### Manual Build and Deploy

~~~bash
# Manual build and deploy
# Build the app from the source directory
cd ./src
dotnet build --configuration Release
# Publish the app into the chuck directory 
dotnet publish -c Release -o ../chuck
# Prepare for deployment by ensuring the zip is created from the correct location
cd ../chuck/
zip -r ../chuck.zip .
az webapp deploy -g ... -n ... --src-path ../chuck.zip
~~~
