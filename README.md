
```
docker build -t sample .
docker build -t sample --build-arg RAILS_ENV_ARG=production --build-arg SECRET_KEY_BASE_ARG=xxx .
docker run --rm --name makoto -d -p 80:3000 -i -t sample:latest
```

```
gcloud sql instances describe appengine-sql
curl -o cloud_sql_proxy https://dl.google.com/cloudsql/cloud_sql_proxy.darwin.amd64
chmod +x cloud_sql_proxy
sudo mkdir /cloudsql
sudo chmod 0777 /cloudsql
cloud_sql_proxy -instances="market-sample:asia-northeast1:market" -dir=/cloudsql

```
gcloud container clusters get-credentials cluster-1
cd docker/rails
gcloud container builds submit --config=cloudbuild.yaml .
kubectl apply -f kube/deployment2.yml
```
