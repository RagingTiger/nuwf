## About
Repo for `NuWF` (NGINX uWSGI Flask) stack template. (NOTE: this repo uses
`Python 3`)

## Purpose
This repo provides a reusable `NuWF stack` as a starting `template` for web 
applications to be built on top of. You can see in the below `directory 
structure` how the template is layed out and how you can use it as a starting
point to build your own web application.

For example: all your static content will go in the `server/nginx/static` 
directory, while all your dynamic `Python 3` content will go in the 
`server/uwsgi/dynamic/python` directory.

## Project Directory Structure
```
.
├── README.md
├── docker-compose.yml
└── server
    ├── nginx
    │   ├── Dockerfile
    │   ├── README.md
    │   ├── config
    │   │   ├── nginx.conf
    │   │   └── webserver.tmpl
    │   └── static
    │       └── robots.txt
    └── uwsgi
        ├── Dockerfile
        ├── README.md
        ├── config
        │   └── uwsgi.ini
        └── dynamic
            └── python
                └── requirements.txt
```
