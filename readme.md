# install concourse pks-vsphere(no nsx-t)


## docs

1. install an ngninx ingress on nodeport

```bash
#apply mandatory ngninx config
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/master/deploy/static/mandatory.yaml
#apply nodeport based nginx
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/master/deploy/static/provider/baremetal/service-nodeport.yaml
```
2. apply a default storage class

```bash
kubectl apply -f default-storage.yml
```

3. deploy concourse

4. modify the manifest files that contain host specific info

```bash
kubectl create ns concourse
kubectl apply --recursive --filename manifests/concourse/
```