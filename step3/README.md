# Step 3 - Multiple Resource YAML

Kubernetes の `Multiple Resource YAML` を使ってみる。

```bash
cd step3
```

## 起動

```bash
kubectl apply -f ./src/spring-boot-example.yml
```

## 削除

```bash
kubectl delete -f ./src/spring-boot-example.yml
```

[<< Previous](../step2) | [Next >>](../step4)
