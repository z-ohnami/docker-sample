
```
docker build -t sample .
```

```
docker build -t sample --build-arg RAILS_ENV_ARG=production --build-arg SECRET_KEY_BASE_ARG=xxx .
```

```
docker run --rm --name makoto -d -p 80:3000 -i -t sample:latest
```
