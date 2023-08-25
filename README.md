# Chuck Norris - Dot Net Sample Application

[![Build Status](https://dev.azure.com/gallowst/docker/_apis/build/status%2Fgallowst.chuck-dotnet?branchName=main)](https://dev.azure.com/gallowst/docker/_build/latest?definitionId=33&branchName=main)

This repository provides a sample .Net 6.0 ASP application implemented using the dot net web framework. It is intended to be used to demonstrate deployment of .Net 6.0 WebApps to Azure.

## Implementation Notes

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
