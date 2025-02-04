This is used to orchestrate containers reliably and efficiently

The general architecture of a kubernetes cluster:
![[Pasted image 20250123163017.webp]]

Now to look at the control plane and nodes in more detail:
![[Pasted image 20250123163417.webp]]
- pods are the key element of nodes 
- in the control plane, the kube-apiserver is the main interaction point
	- etcd provides a basic key value store
	- kube-scheduler handles the pods
	- cloud-controller-manager interacts with cloud platforms
	- kube-controller-mananger
- kube-proxy gives communication from nodes to the outside world

Overview:
![[Pasted image 20250123164257.webp]]