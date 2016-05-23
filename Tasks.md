# Tasks

These are the different tasks which we will carry out during the workshop. The different tasks is (hopefully) in order from easy to more difficult tasks with Ansible. However feel free to explore the different possibilities which Ansible provides if the tasks does not suit your cup of tea.

The tasks are to install nginx (to be used as a reverse proxy), postgresql, and a simple java-application. The Java-application will run on port 8080 and be proxied through nginx.

## Task 1
You can use the apt-module to solve it (assuming Ubuntu)

Install a couple of useful utilities, `vim`, `git` and `java8 (openjdk)`

## Task 2
Install nginx or apache, whichever you prefer, and ensure that the service is running.

## Task 3
Install postgresql-database. Ensure that it is running and add both a database and a user. You can name the database (and the user) `ansible_workshop` for example. See the postgresql module for inspiration for how to solve this task.

## Task 4
Install and run the Java-application.

### Intro to the application

To Run the application:
1. Run with java -jar app/helloworld.jar server app/helloworld.yml
2. The application should now listen on port 8080 and have an administration panel at port 8081.
3. Test `localhost:8080/?name="palt"` should return
```
{
  id: 1,
  content: "Hello, "palt"!"
}
```

The files you need to run the application is `app/helloworld.jar` and  `app/helloworld.yml`(configuration file). Copy these files to the server or just run them if you have built the application on the server itself.

If you are feeling great you can make a systemd-job to autostart the application. If not just run it with `screen` for this workshop.

Before startup you need to configure the database connection. When the application and database are on the same server this is very simple. Edit `helloworld.yml` and change the password for the database connection to url: jdbc:postgresql://localhost/ansible-workshop.

When the application starts it will try to connect to the database and will give an error if this fails.

When everything is running the application contains 3 (badly implemented) endpoints to interact with the database. The are located under `http://serverip/database/`. The resources are

* create - GET: Makes a table `something` if it doesn't exist.
* insert - POST: Accepts the following JSON in body `{"status" : "something"}`
* list - GET: Lists everything in the `something`-database table

## Task 5
Configure Nginx (or apache) to be a reverse proxy in front of the application.
