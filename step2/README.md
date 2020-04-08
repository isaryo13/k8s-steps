# Step 2 - Service

Kubernetes の `Service` を使ってみる。

```sh
cd step2
```

## DNS Debugger

DNS デバッグのために `dnsutils` Pod を起動 (参考: [Debugging DNS Resolution - Kubernetes](https://kubernetes.io/docs/tasks/administer-cluster/dns-debugging-resolution/))
```sh
kubectl apply -f ../tools/dnsutils.yml
```

## MySQL

起動
```sh
kubectl apply -f ./src/mysql-pod.yml \
              -f ./src/mysql-svc.yml
```

ポートフォワーディング
```sh
kubectl port-forward svc/mysql-svc 3306
```

名前解決
```sh
kubectl exec -it dnsutils -- nslookup mysql-svc
```

## Redis

起動
```sh
kubectl apply -f ./src/redis-pod.yml \
              -f ./src/redis-svc.yml
```

ポートフォワーディング
```sh
kubectl port-forward svc/redis-svc 6379
```

名前解決
```sh
kubectl exec -it dnsutils -- nslookup redis-svc
```

## App

起動
```sh
kubectl apply -f ./src/app-pod.yml \
              -f ./src/app-svc.yml
```

ポートフォワーディング
```sh
kubectl port-forward svc/app-svc 8080
```

ノードポートアクセス
```sh
open http://$(minikube ip):30080/
```

## 削除

リソース指定
```sh
kubectl delete pod app-pod redis-pod mysql-pod dnsutils
kubectl delete svc app-svc redis-svc mysql-svc
```

マニフェストファイル指定
```sh
kubectl delete -f ./src/mysql-pod.yml \
               -f ./src/mysql-svc.yml \
               -f ./src/redis-pod.yml \
               -f ./src/redis-svc.yml \
               -f ./src/app-pod.yml \
               -f ./src/app-svc.yml \
               -f ../tools/dnsutils.yml
```

[<< Previous](../step1) | [Next >>](../step3)
