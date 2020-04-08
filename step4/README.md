# Step 4 - Volume

Kubernetes の `PersistentVolume`, `PersistentVolumeClaim` を使ってみる。

```sh
cd step4
```

## 起動

```sh
kubectl apply -f ./src/spring-boot-example.yml
```

MySQL, Redis の Pod だけ再起動
```sh
kubectl delete pod mysql-pod redis-pod
kubectl apply -f ./src/mysql.yml \
              -f ./src/redis.yml
```

## 削除

```sh
kubectl delete -f ./src/spring-boot-example.yml
```

[<< Previous](../step3) | [Next >>](../step5)
