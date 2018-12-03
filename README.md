# Basic Docker-Compose package

## Install

1. Clone this repository. 
1. Choose suitable branch.
1. Remove `.git` folder.
1. Move `docker` folder into your project root.

## Set-up

1. `cp env-example .env`
1. Configure containers using .env file: 
  * Change `APPLICATION_NAME` in `.env` file. 
  * Change PHP version (default is 7.2) 
1. `docker-compose up -d` 

## .env file

You can explore various options in the `.env` file.

After each change you need to run `docker-compose down && docker-compose build`. 

## Accessing the app

You can access your app through http://localhost or add custom hosts file record like `127.0.0.1 app.test`.


## Troubleshooting

### There are `Failed to fetch` apt package manager errors during build
Rebuild the failing container with `--no-cache` option. 
```
docker-compose build --no-cache php-fpm
```

### Google Chrome is enforcing HTTPS connection
Use less generic TLD for custom hosts file record. Ex. `.test`. 


