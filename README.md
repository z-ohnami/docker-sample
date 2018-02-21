
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

```
gcloud container clusters get-credentials cluster-1
kubectl create secret generic cloudsql-instance-credentials --from-file=credentials.json={jsonfile}
kubectl create secret generic cloudsql-db-credentials --from-literal=username=db_proxy
kubectl create secret generic cloudsql-user --from-literal=username=hoge
cd docker/rails
gcloud container builds submit --config=cloudbuild.yaml .
kubectl apply -f kube/deployment2.yml
```

```
kubectl delete  nginx-deployment
gcloud container clusters delete cluster-1
```

```
docker run --rm -d -p 9200:9200 -i -t elasticsearch:5.6.7-alpine
docker exec -it {container id} /bin/bash
```

```
curl -XGET http://localhost:9200
curl -XGET http://localhost:9200/properties?pretty
curl -XGET http://localhost:9200/properties/areas/_count?pretty
curl -XPUT http://localhost:9200/test_index/log/1 -d '{"host":"localhost", "message":"test message is fine."}'
curl -XGET http://localhost:9200/test_index/log/1
curl -XGET http://localhost:9200/test_index/_search -d '{}'
curl -XGET http://localhost:9200/test_index/_search -d '{"query":{"query_string":{"query": "message:test"}}}'
curl -XPOST http://localhost:32771/_bulk -H 'Content-Type: application/json' --data-binary "@properties_index3-1.json"
```

```
cat properties_cache2.json | redis-cli --pipe -h localhost -p 32768
```
