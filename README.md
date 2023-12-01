# Bucarest Bank (no CSS)

- This is a demo online banking application that illustrates the use of the BUCAREST architectural style.
- It uses the JavaScript frameworks Alpine.js and HTMX on the front-end, along with Bootstrap CSS for layout and styling.
- The back-end uses Spring Boot with the Thymeleaf template engine.

## Update
>This version has no Bootstrap or CSS at all, and cleaner HTML (body/header/main-section/footer metaphor). It can be used as a base setup to then experiment with CSS toolkits.

>This version is configured to build a war package for deployment into a Tomcat server.

## Install:

Run from project dir:

`mvn install`

## Run

Run from project dir:

`mvn spring-boot:run`

Then point your browser at `http://localhost:8081` to see the online banking screen. HTML coding changes under `src/main/resources` are dynamic but require page refreshes.

Also open the browser console to see the HTTP requests and responses.

## Deploy

Build a war file:

`mvn clean package`

## NOTES:

- Doing a transfer or making a payment is a POST request.
- The HTTP response will have two fine-grained application headers 
- `"Hx-Trigger : account.currentBalance"`
- `"Hx-Trigger : transactions"`
- This then triggers two of the three visual components on the page to refresh themselves through follow-up GET requests.
