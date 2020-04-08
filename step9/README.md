# Step 9 - Kustomization

Kubernetes の `Kustomization` を使ってみる。

```
step9/src
├── app
│   ├── application.properties
│   ├── deployment.yml
│   ├── ingress.yml
│   └── service.yml
├── mysql
│   ├── deployment.yml
│   ├── service.yml
│   └── storage.yml
├── mysql
│   ├── deployment.yml
│   ├── service.yml
│   └── storage.yml
├── kustomization.yml
└── namespace.yml
```

```bash
cd step9
```

## ビルド結果表示

```bash
kubectl kustomize ./src
```

## 起動

```bash
kubectl apply -k ./src
```

## 削除

```bash
kubectl delete -k ./src
```

[<< Previous](../step8)
