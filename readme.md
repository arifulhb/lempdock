# LEMP Dock
A docker image for LEMP Stack Development

[![LEMP DockClone Counter](https://img.shields.io/github/downloads/arifulhb/lempdock/total.svg)]()

## Installation / Usage

Run following commands to clone the repo, build and run LEMP Dock docker image.

    git clone git@github.com:arifulhb/lempdock.git lemptdock
    cd lempdock
    lemp/build
    lemp/run
    
### Usage
- Build the docker image : 
    - Use command `lemp/build` to build the lempdock image.
- Run the docker image: 
    - Use command `lemp/run` to run the containers
- Stop the container:
    - `lemp/stop` to stop the containers
- SSH to `php-fpm` container
    - `lemp/ssh` and you'll be in `/var/www` directory of `php-fpm` container.
    

## Included Softwares:
1. Debian `9.8` / stretch OS
2. PHP `7.2`
3. Nginx
4. MySQL `5.7`
5. Compose `1.8` for PHP Package Management
6. Nodejs `10.15`
7. NPM `6.4`
8. git `2.11`


## Documentation
### PHP-FPM
Add your source code in `www` directory and this source code will be available in your `php-fpm` and `nginx` containers `/var/www` diectory.
### Nginx
To add a new site in your LEMP Dock, you need to add a new nginx config file in `images/nginx/sites/` directory. 
Create a copy of the `images/nginx/sites/default.conf` file and edit `server_name` and `root` according to your application.
 
### MySQL
##### Default settings to connect from SequelPro or MySQL Workbench   

    host: 127.0.0.1
    user: root
    pass: root
    port: 33066


##### Default settings to connect from PHP App inside `php-fpm` container
    
    host: mysql
    port: 3306
    user: root
    pass: root