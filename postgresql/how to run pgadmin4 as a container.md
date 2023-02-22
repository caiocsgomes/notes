```sh
docker run -p 80:80 \
    -e 'PGADMIN_DEFAULT_EMAIL=postgres@postgres.com' \
    -e 'PGADMIN_DEFAULT_PASSWORD=postgres' \
    -v pgadmin4:/var/lib/pgadmin \
    -d dpage/pgadmin4
```

https://www.pgadmin.org/docs/pgadmin4/latest/container_deployment.html