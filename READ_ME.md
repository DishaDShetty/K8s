kubectl port-forward nginx 8080:80


https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack:
1. helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
2. helm repo update
3. helm install prometheus prometheus-community/kube-prometheus-stack
4. kubectl get pods
5. kubectl get all
6. kubectl get services
7. kubectl get deployments
8. kubectl port-forward deployment/prometheus-grafana 3000[deployment/deplyment name: port on which the pod is running on]
9. admin: prom-operator
10. kubectl port-forward prometheus-prometheus-kube-prometheus-prometheus-0 9090[pod:9090]
11. helm ls
12. kubectl get servicemonitor
13. helm install my-release oci://registry-1.docker.io/bitnamicharts/nginx -f values.yaml
14. 

** Please be patient while the chart is being deployed **

MongoDB&reg; can be accessed on the following DNS name(s) and ports from within your cluster:

    my-release-mongodb.default.svc.cluster.local

To get the root password run:

    export MONGODB_ROOT_PASSWORD=$(kubectl get secret --namespace default my-release-mongodb -o jsonpath="{.data.mongodb-root-password}" | base64 -d)

To connect to your database, create a MongoDB&reg; client container:

    kubectl run --namespace default my-release-mongodb-client --rm --tty -i --restart='Never' --env="MONGODB_ROOT_PASSWORD=$MONGODB_ROOT_PASSWORD" --image docker.io/bitnami/mongodb:7.0.2-debian-11-r0 --command -- bash

Then, run the following command:
    mongosh admin --host "my-release-mongodb" --authenticationDatabase admin -u $MONGODB_ROOT_USER -p $MONGODB_ROOT_PASSWORD

To connect to your database from outside the cluster execute the following commands:

    kubectl port-forward --namespace default svc/my-release-mongodb 27017:27017 &
    mongosh --host 127.0.0.1 --authenticationDatabase admin -p $MONGODB_ROOT_PASSWORD
