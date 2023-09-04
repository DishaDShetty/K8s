1. controller -  Its main task is to watch for changes in the state of the objects, and make sure that the actual state converges towards the new desired state.
ref file - https://sysdig.com/blog/how-to-monitor-kube-controller-manager/#:~:text=Kubeadm%20sets%20the%20kube%2Dcontroller,.0.1%3A10257%2Fmetrics.
2. etcd - distributed key-value store used to hold and manage the critical information that distributed systems need to keep running.
ref file - https://etcd.io/docs/v3.1/op-guide/configuration/#:~:text=etcd%20is%20configurable%20through%20command,It%20applies%20to%20all%20flags.
3. scheduler - uses a database to persist information concerning which tasks to run and when.
ref file - 



final - https://github.com/AndriyKalashnykov/kind-cluster/blob/main/k8s/helloweb-deployment.yaml