# Project Onboarding

## Requirements
* Docker
* Docker Compose
* NodeJS / NVM (Node version Manger)
    * Some projects might not work with recent versions of NodeJS

## Step-by-step

- Run `cp .envsample .env`
    - This will create a env file that docker-compose will consume

### Configuring Database
- Run `docker-compose up postgres`. There should a postgres database running on port 5433
    - The default credentials are on `.envsample`
- Connect to the database using any tool - Dbeaver, PgAdmin....
- Download *XPD-Sample-xpd-\*.tar* [from here](https://drive.google.com/drive/folders/1xg1xwXJIdIsZoiaFihu6Tk5CAhQktNM8)
- Restore the backup into the XPD database
- Check if the database was created
- You can close the terminal now

### Running Basic Services
- Run `docker-compose up setup-build`
    - This is done once
- Run `docker-compose up postgres setup`
- Try on the browser `http://localhost:8080/xpd-setup-api/setup/well/list`. You should see:
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

### Running all remaining services
- Run `docker-compose up`
- Keep trying on the browser
    - `http://localhost:9000/setup.html`
    - `http://localhost:8081/health`
- When both works, we should be ready to go


## Resources

### Database Dumps
https://drive.google.com/drive/folders/1xg1xwXJIdIsZoiaFihu6Tk5CAhQktNM8?usp=share_link

### Readonly repo token
rfQNLXdrRM87q-Zy2ajK
