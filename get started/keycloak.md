# GET STARTED WITH KEYCLOAK

## SETUP

Make sure docker is installed in your machine.

## START KEYCLOAK

1. From the terminal, run the following command to start keycloak

```shell
docker run -p 8080:8080 -e KEYCLOAK_ADMIN=admin -e KEYCLOAK_ADMIN_PASSWORD=admin quay.io/keycloak/keycloak:22.0.1 start-dev
```

2. Go to <http://localhost:8080/admin> to access the admin panel
