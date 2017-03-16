# Docker-Mezzanine
Mezzanine for Django running with Docker Compose.
Configured to create separate container for running PostgreSQL,
 and creates the data volume in the project directory.

## Prerequisites
* GIT
* Docker & Docker Compose

## Command Line Installation
1. Clone the project into a local directory
   * `git clone https://github.com/Maaack/Docker-Mezzanine.git YourDumbProjectName`

2. Go into your dumb project directory
   * `cd YourDumbProjectName`

3. Double check that things checked out
   * `ls -al`
   * It should list files, like those shown here: https://github.com/Maaack/Docker-Mezzanine

4. Set the local settings
   * `mv default_local_settings.py local_settings.py`
   * You should also go into the file and change the SECRET_KEY

5. Run Docker Compose locally
   * `docker-compose up` 
   * You might need to run Docker Compose as the admin
   * `sudo docker-compose up`

### Install the Database ###
*Looking for suggestions on how to improve this part*

1. Identify your container
   * `sudo docker ps`

2. Run bash interactively in the container
   * `$> sudo docker exec -it CONTAINER_NAME /bin/bash`
   * You are inside the container if you see this prompt
   * `CONTAINER_NAME$>`

3. Create the database
   * `CONTAINER_NAME$> python manage.py createdb`

4. Exit the container
   * `CONTAINER_NAME$> exit`

### All done ###
* Open your browser and go to http://localhost:8000/ 
  * You should see all sorts of amazing things there
  * Or error messages, very helpful error messages

## Additional Resources ##
* Writing your first Django App Tutorials: https://docs.djangoproject.com/en/1.10/intro/tutorial01/
* Developer guide for working with Mezzanine: http://mezzanine.jupo.org/docs/index.html
* Mezzanine homepage: http://mezzanine.jupo.org/