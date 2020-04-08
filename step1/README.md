# Step 1 - `Pod`

Kubernetes の `Pod` を使ってみる。

```sh
cd step1
```

## MySQL

起動
```sh
kubectl apply -f ./src/mysql-pod.yml
```

接続
```sh
kubectl exec -it mysql-pod -- /bin/bash
```

接続（コンテナ指定）
```sh
kubectl exec -it mysql-pod -c mysql -- /bin/bash
```

ポートフォワーディング
```sh
kubectl port-forward pod/mysql-pod 3306
```

## Redis

起動
```sh
kubectl apply -f ./src/redis-pod.yml
```

接続
```sh
kubectl exec -it redis-pod -- /bin/bash
```

接続（コンテナ指定）
```sh
kubectl exec -it redis-pod -c redis -- /bin/bash
```

ポートフォワーディング
```sh
kubectl port-forward pod/redis-pod 6379
```

## App

起動前に MySQL, Redis の Pod の IPアドレスで `app-pod.yml` の接続設定を編集。

起動
```sh
kubectl apply -f ./src/app-pod.yml
```

ポートフォワーディング
```sh
kubectl port-forward pod/app-pod 8080
```

## 削除

リソース指定
```sh
kubectl delete pod app-pod redis-pod mysql-pod
```

マニフェストファイル指定
```sh
kubectl delete -f ./src/mysql-pod.yml \
               -f ./src/redis-pod.yml \
               -f ./src/app-pod.yml
```

[Next >>](../step2)
