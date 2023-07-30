# INTRODUCTION

This is a documentation of the processes and technologies used to develop an application using a microservice achitecture with keycloak IAM, krakenD api gateway, django for apis and nextjs as a frontend.

## ARCHITECTURE

The architecture used in the `MICROSERVICE ARCHTECTURE`

[read about this architecture](https://cloud.google.com/learn/what-is-microservices-architecture)


## API ACCESS, AUTHENTICATION AND AUTHORIZATION

The above mentioned architecture calls for the use of a separate authentication service. In this project, [KEYCLOAK](https://www.keycloak.org/) is being used for that purpose.

Also [KRAKEND](https://www.krakend.io/) is being used as an API gateway.

Together these two services complete the authentication and authorization architecture for this project.

[Read more about this](https://www.krakend.io/docs/authorization/keycloak/)

![keycloak and krakend integration](/images//krakend-keycloak-integration-workflow.png)


## COMPONENTS

This sample project is comprised of a sample service (a django rest api backend with sample endpoints) and a nextjs frontend application that should consume the api. We will be using docker to run the projects as it is in the `/project/docker-compose.yml` file. All configurations are in the `/project/config/*` folder.

### Links to the repos of samples used in the projects
- django service => [https://github.com/jackkweyunga/drf_oidc_example](https://github.com/jackkweyunga/drf_oidc_example)
- nextjs 13 frontent => [https://github.com/jackkweyunga/nextjs-keycloack-example](https://github.com/jackkweyunga/nextjs-keycloack-example)

# RUN THE PROJECT

Make sure docker is installed in your machine [Docker installation](https://docs.docker.com/engine/install/).

```shell
git clone
cd project
docker compose up -d

```

## Setup Keycloak

- [x] Got to the keycloack instance at => [http://localhost:8080](http://localhost:8080) . 

- [x] Login with credentials below;
  - username: `admin`
  - password: `admin`

- [x] Once inside, create a new real by importing a sample realm `the-ream` found in `./project/config/keycloak/realm-export.json`

- [x] After the import is successful, two clients [`ms-frontend` and `svc1`] will be available in a real called `the-real`.

- [x] Within the real got to the client page for `ms-frontend` and `svc1` and regenerate the client secrete. Copy the client secrets and replace with the ones in `/project/config/frontend/.env` and `/project/config/service1/.env` respectively.
  - Restart the project with command `docker compose up -d` to enact the changes.
  
- [x] With in this realm, create a user with whom you will login in to the frontend. Remember to set the password for this user.


## Test the project

Go to the frontend application at => [http://localhost:4000](http://localhost:4000) . Once there you'll see the request made to the public endpoint of the django service backed via the krakenD api gateway. Finally click the login link to be redirected to the kecloak instance for authentication. After authentication, the protected pages of the frontend will accessible.

If everything works correctly, you should be able to see the following in the frontend;

![Alt text](/images/image.png)

