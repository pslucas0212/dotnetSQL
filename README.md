# Notes regarding my .Net tests

## Install SQL Server 2019 on Mac OS in Docker
Reference Article - https://docs.microsoft.com/en-us/sql/linux/quickstart-install-connect-docker?view=sql-server-ver15&pivots=cs1-bash

- docker pull mcr.microsoft.com/mssql/server:2019-latest
- docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=Passw0rd!' -p 1433:1433 --name sql1 -h sql1 -d mcr.microsoft.com/mssql/server:2019-latest 
- Docker ps -a “check if running”
- docker stop sql1
- docker rm sql1
- docker list - list images
- docker rmi <container ID> - remove image

## Install SQLcmd tool on Mac OS
Reference Article - https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-setup-tools?view=sql-server-ver15#macos

## Install Azure Data Studio
https://docs.microsoft.com/en-us/sql/azure-data-studio/download-azure-data-studio?view=sql-server-2017

## Find container IP address
docker inspect -f "{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}" 67ec9fcc0880

## Connection String setting to access MS SQL running in Docker Container
Reference Article - Running and Connecting to SQL Server On Your Mac - https://www.linkedin.com/pulse/running-connecting-sql-server-your-mac-michael-ahearn/

        "ConnectionStrings": {
                "MovieContext": "Server=127.0.0.1,1433;Database=MovieList;User ID=sa;Password=Passw0rd!"
            }
