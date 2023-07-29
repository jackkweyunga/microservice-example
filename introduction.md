# INTRODUCTION

This is a documentation of the processes and technologies used to develop an application using a microservice achitecture with django for apis and nextjs as a frontend.

## ARCHITECTURE

The architecture used in the `MICROSERVICE ARCHTECTURE`

[read about this architecture](https://cloud.google.com/learn/what-is-microservices-architecture)


## AUTHENTICATION AND AUTHORIZATION

The above mentioned architecture calls for the use of a separate authentication service. In ukumbi, [KEYCLOAK](https://www.keycloak.org/) is being used for that purpose.

Also [KRAKEND](https://www.krakend.io/) is being used as an API gateway.

Together these two services complete the authentication and authorization architecture for ukumbi.

[Read more about this](https://www.krakend.io/docs/authorization/keycloak/)

![keycloak and krakend integration](/images//krakend-keycloak-integration-workflow.png)


## COMPONENTS

This sample project is comprised of a sample service (a django rest api backend with sample endpoints) and a nextjs frontend application that should consume the api. We will be using docker to run the projects as it is in the `docker-compose` file. All configurations are in the `config` folder.

### Links to the repos containing the projects
- django service => [https://github.com/jackkweyunga/drf_oidc_example](https://github.com/jackkweyunga/drf_oidc_example)
- nextjs 13 frontent => [https://github.com/jackkweyunga/nextjs-keycloack-example](https://github.com/jackkweyunga/nextjs-keycloack-example)




