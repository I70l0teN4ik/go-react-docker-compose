# docker-compose for web app with Golang backend
### Both apps support hot-reload

1. Clone BE and FE to `./webroot` corresponding subdirectories
2. Run `docker-compose up -d`

- BE will be exposed under `http://localhost`
- FE will be exposed under `https://localhost`

Nginx template is prepared to proxypass the GraphQL calls on `/gql` endpoint.
This allows to avoid any CORS problems. 
