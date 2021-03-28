# k8s-statefulset-web-app
# kubectl apply -k ./
# kubectl get service -n dev nginx
# kubectl get statefulset web
# kubectl get pods -w -l app=nginx
# for i in 0 1; do kubectl exec "web-$i" -- sh -c 'hostname'; done
# kubectl run -i --tty --image busybox:1.28 dns-test --restart=Never --rm
# nslookup web-0.nginx
# kubectl get pod -w -l app=nginx
# kubectl delete pod -l app=nginx
# kubectl get pod -w -l app=nginx
# kubectl get pvc -l app=nginx
# for p in 0 1 2; do kubectl get pod "web-$p" --template '{{range $i, $c := .spec.containers}}{{$c.image}}{{end}}'; echo; done
# kubectl patch statefulset web --type='json' -p='[{"op": "replace", "path": "/spec/template/spec/containers/0/image", "value":"gcr.io/google_containers/nginx-slim:0.8"}]'
# kubectl patch statefulset web -p '{"spec":{"updateStrategy":{"type":"RollingUpdate"}}}'

# Staging an Update
# kubectl patch statefulset web -p '{"spec":{"updateStrategy":{"type":"RollingUpdate","rollingUpdate":{"partition":3}}}}'
# kubectl patch statefulset web --type='json' -p='[{"op": "replace", "path": "/spec/template/spec/containers/0/image", "value":"k8s.gcr.io/nginx-slim:0.7"}]'
