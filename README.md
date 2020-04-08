# Kubernetes 勉強素材

## 環境

- [docker](https://docs.docker.com/install/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
- [minikube](https://kubernetes.io/docs/tasks/tools/install-minikube/)
- [virtualbox](https://www.virtualbox.org/)

## インストールと初期設定

### Mac

```sh
brew install docker virtualbox minikue kubectl
minikube start --vm-driver=virtualbox
minikube addons enable ingress
kubectl config use-context minikube
```

### Windows

`TODO`

## 利用するイメージ

- [isaryo13/spring-boot-example](https://hub.docker.com/repository/docker/isaryo13/spring-boot-example)
- [mysql](https://hub.docker.com/_/mysql)
- [redis](https://hub.docker.com/_/redis)

## ステップ

[<< この資料のゴールはこちら >>](./goal)

- [Step 1 - Pod](./step1)
- [Step 2 - Service](./step2)
- [Step 3 - Multiple Resource YAML](./step3)
- [Step 4 - Volume](./step4)
- [Step 5 - Deployment](./step5)
- [Step 6 - Ingress](./step6)
- [Step 7 - ConfigMap/Secret](./step7)
- [Step 8 - Namespace](./step8)
- [Step 9 - Kustomization](./step9)

## デバッグ・動作確認ツール

### Kubernetes Dashboard

[isaryo13/kubernetes-dashboard](https://github.com/isaryo13/kubernetes-dashboard)

```bash
$ kubectl apply -f ./tools/kubernetes-dashboard.yaml
$ kubectl proxy
```

### DNS Debugger

[Debugging DNS Resolution - Kubernetes](https://kubernetes.io/docs/tasks/administer-cluster/dns-debugging-resolution/)

```bash
kubectl apply -f ./tools/dnsutils.yml
```
