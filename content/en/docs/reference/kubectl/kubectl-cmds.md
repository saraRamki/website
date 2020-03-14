---
title: kubectl Commands
---
	2.Add the Docker repository:
	sudo add-apt-repository    "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
	   $(lsb_release -cs) \
	   stable"
	
	3.Get the Kubernetes gpg key:
	curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
	
	4.Add the Kubernetes repository: (create the file  add the lines )
	cat << EOF | sudo tee /etc/apt/sources.list.d/kubernetes.list
	deb https://apt.kubernetes.io/ kubernetes-xenial main
	EOF
	
	5.Update your packages:
	sudo apt-get update
	
	6.Install Docker, kubelet, kubeadm, and kubectl:
	sudo apt-get install -y docker-ce=18.06.1~ce~3-0~  ubuntu kubelet=1.13.5-00 kubeadm=1.13.5-00 kubectl=1.13.5-00
	
	7.Hold them at the current version:
	sudo apt-mark hold docker-ce kubelet kubeadm kubectl
	
	8.Add the iptables rule to sysctl.conf:  (tee command to append the file)
	echo "net.bridge.bridge-nf-call-iptables=1" | sudo tee -a /etc/sysctl.conf
	
	9.Enable iptables immediately:  (-p option for a file )
	sudo sysctl -p            

[kubectl Command Reference](/docs/reference/generated/kubectl/kubectl-commands/)
