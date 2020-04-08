# Step 5 - Deployment

Kubernetes の `Deployment` を使ってみる。

```bash
cd step5
```

## 起動

```bash
kubectl apply -f ./src/spring-boot-example.yml
```

## 履歴の表示

```bash
kubectl rollout history deploy app-deploy -n spring-boot-example
```

```bash
kubectl describe deployment -n spring-boot-example
```

## ロールバック

一つ前のリビジョン
```bash
kubectl rollout undo deploy app-deploy -n spring-boot-example
```

リビジョン指定
```bash
kubectl rollout undo deploy app-deploy --to-revision=1 -n spring-boot-example
```

## スケーリング

```bash
kubectl scale deployment/app-deploy --replicas=3 -n spring-boot-example
```

## 削除

```bash
kubectl delete -f ./src/spring-boot-example.yml
```

[<< Previous](../step4) | [Next >>](../step6)
