
# PRIVATE REGISTRY USING VERDACCIO DOCKER IMAGE

1. Install Docker on your machine (https://docs.docker.com/install/)
2. Clone this repo and cd into the repo
3. use the docker-compose file to start the verdaccio server
4. use the config.yaml file to configure the server if needed
5. use the htpasswd file to add users to the server -- Refer Login Section

## Docker Compose File
    starts the verdaccio server on port 4873. You can change the port if you want.
    version: '3'
    services:
        verdaccio

## Config.yaml file
    Uplinks are links to npmjs https://registry.npmjs.org/
    https://verdaccio.org/docs/uplinks

## Storage
    All the packages are stored in the storage folder and cached by default. 
    If you would like to save space, you can change the cache to false in the config.yaml file.

    There will be a data folder created in the storage folder. This is where the packages cached and stored. This folder is part of git ignore, so that it is not pushed to the repo.

## Starting the docker container
    docker-compose up -d

## To see docker logs
    docker-compose logs --follow verdaccio
    You can also see the docker logs on the docker desktop app if you have it installed. 

## LOGIN
    npm adduser --registry http://localhost:4873/
    username: admin
    password: 123456


There is a plenty of documentation available on the verdaccio website. 
Please refer https://verdaccio.org/docs/what-is-verdaccio for more information.



