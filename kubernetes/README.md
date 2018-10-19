Kubernetes cluster setup

	Prerqueties-------
		Vagrant v2.2.0
		VirtualBox 5.2.0
		8 GB RAM on host
		50 GB storage

	Running process-----
		vagrant up --provision

		Cluster should be up and running on vm.

	Accsess on your host browser: http://localhost:8001/api/v1/namespaces/kube-system/services/https:kubernetes-dashboard:/proxy/#!/overview