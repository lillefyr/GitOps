
https://www.youtube.com/watch?v=r50tRQjisxw
From https://github.com/gitops-workshop/poor-mans-gitops


# Demo: Poor Man's GitOps

### 1. Build The Agent

```
docker build -t my-agent agent
```

### 2. Install The Agent

```
kubectl -n default apply -f agent/install.yaml
```

Wait for the agent to apply your manifests:

```
watch kubectl -n default get all
```

<!--
### Publish Agent

```
docker login
docker tag my-agent ariedeldocker/agent
docker push ariedeldocker/agent
```
-->

### Clean-Up

```
kubectl -n default delete -f agent/install.yaml
kubectl -n default delete pod my-app
```
