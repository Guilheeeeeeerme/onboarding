# Project Onboarding

## Requirements
* Docker
* Docker Compose
* Optional (only if you are going to develop something)
    * NodeJS / NVM (Node version Manger)
        * Some projects might not work with recent versions of NodeJS

## Initial steps
- Run `sh clone.sh` to clone all the projects
- Run `cp .envsample .env`
    - This will create a env file that docker-compose will consume
- *Make sure your .env files is pointing to where you are expecting it to point*

---
## Configuring Database
### If you dont have a postgres instace running on your machine
- Run `docker-compose up postgres`. 
- There should a postgres database running on port 5433
- There should exist a `xpd` database on that instance
- The default credentials are on `.envsample`

### If you do have a postgres instace running on your machine
- Make sure the `.env` file is pointing to it

## Getting ready with the database
- Connect to the database using any tool - Dbeaver, PgAdmin....
- Download *XPD-Sample-xpd-\*.tar* [from here](https://drive.google.com/drive/folders/1xg1xwXJIdIsZoiaFihu6Tk5CAhQktNM8)
- Restore the backup into the XPD database
- You can close the terminal now

---
## Running Basic Services
- Run `docker-compose up postgres setup`
- Wait for it
- Try on the browser `http://localhost:8080/xpd-setup-api/setup/well/list`. Until you see:
```json
{
    "timestamp": 1677870307362,
    "code": 200,
    "status": "success",
    "message": "List Well Sucessfully!",
    "data": [{
        "id": 1,
        "name": "Well Sample",
        "current": false,
        "running": false,
        "airGap": 30,
        "waterDepth": 2000,
        "sections": []
    }],
    "wrappedResponse": true
}
```
- You can close the terminal now

---
## Running all remaining services
- Run `docker-compose up`
- Keep trying on the browser
    - `http://localhost:9000/auth.html`
    - `http://localhost:8081/health`
- When both works, we should be ready to go
- Crendentials:
    - admin
    - rzxtec123

### Database Dumps
https://drive.google.com/drive/folders/1xg1xwXJIdIsZoiaFihu6Tk5CAhQktNM8?usp=share_link
