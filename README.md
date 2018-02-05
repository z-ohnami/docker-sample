
docker build -t sample .
docker build -t sample . --build-arg RAILS_ENV_ARG=development SECRET_KEY_BASE_ARG=xxx
docker run --name makoto -p 80:3000 -i -t -d sample:latest

