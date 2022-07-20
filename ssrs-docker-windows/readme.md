# SQL Server Reporting Services in Docker

creates a fresh install of SSRS in a container - pretty useful for dev / test - not for production use!

https://hub.docker.com/r/thiagomoreiraboby/ssrs-windows

## Run it

In addtion it accepts two more env variables: </br>

- **ssrs_user**: Name of a new admin user that will be created to login to report server
- **ssrs_password**: Sets the password for the admin user

example:

```
docker run -d -p 1433:1433 -p 80:80 -v C:/temp/:C:/temp/ -e sa_password=<YOUR SA PASSWORD> -e ACCEPT_EULA=Y -e ssrs_user=SSRSAdmin -e ssrs_password=<YOUR SSRSAdmin PASSWORD> --memory 6048mb thiagomoreiraboby/ssrs-windows
```

then access SSRS at http://localhost/reports and login using ssrs_user

## Tips

- **-p 80:80** to access report manager in browser
- **--memory 6048mb** to bump RAM
