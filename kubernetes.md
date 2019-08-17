# Kubernetes dashboard
```
apiVersion: v1
kind: Service
metadata:
  labels:
    app: kubernetes-dashboard
  name: kubernetes-dashboard-katacoda
  namespace: kube-system
spec:
  ports:
  - port: 80
    protocol: TCP
    targetPort: 9090
    nodePort: 30000
  selector:
    app: kubernetes-dashboard
  type: NodePort

```


## Attaching local images

`eval $(minikube docker-env)` for each shell session

- Set the environment variables with eval $(minikube docker-env)
- Build the image with the Docker daemon of Minikube (eg docker build -t my-image .)
- Set the image in the pod spec like the build tag (eg my-image)
- Set the imagePullPolicy to Never, otherwise Kubernetes will try to download the image.

