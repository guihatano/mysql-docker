# mysql-docker
Git repo for Dockerfiles and scripts for MySQL Server based on Ubuntu 14.04

It's a modification of the official repo.

Example usage: 
     `$ docker run --name mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d guihatano/mysql:tag`

Using volume:
     `$ docker run --name mysql -v /my/own/datadir:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d guihatano/mysql:tag`

where `mysql` is the name you want to assign to your container, `my-secret-pw` is the password to be set for the MySQL root user and `tag` is the tag specifying the MySQL version you want.

Supported tags
---------------------

 - `5.5`
 - `5.6` and `latest`

Environment variables
---------------------

The environment variables are the same of official repo:

 - `MYSQL_ROOT_PASSWORD`: This variable is mandatory and specifies the password that will be set for the MySQL `root` superuser account. In the above example, it was set to `my-secret-pw`.
 - `MYSQL_DATABASE`: A database to automatically create. If not provided, does not create a database.
 - `MYSQL_USER`: A user to create that has access to the database specified by `MYSQL_DATABASE`.
 - `MYSQL_PASSWORD`: The password for `MYSQL_USER`. Both variables are required for a user to be created.
 - `MYSQL_ALLOW_EMPTY_PASSWORD`: This is an optional variable. Set to `yes` to allow the container to be started with a blank password for the root user. _NOTE:_ Setting this variable to `yes` is not recommended unless you really know what you are doing, since this will leave your MySQL instance completely unprotected, allowing anyone to gain complete superuser access.
