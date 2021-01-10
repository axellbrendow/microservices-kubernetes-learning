# Horizontal Pod Autoscaler example

To create this Deployment in your cluster:

```
kubectl apply -f .
```

To test the auto scaler, run `kubectl run -it loader --image=busybox /bin/sh`

And then, inside busybox, run `while true; do wget -q -O- http://php-apache-hpa.default.svc.cluster.local; done`

In another terminal, you can see auto scaler working with `kubectl get hpa`. If you wanna watch the metrics, run `watch kubectl get hpa`
