
https://github.com/vimallinuxworld13/Kubernetes_MultiNode_Cluster_using_Kubeadm
create a master node on aws with ex2

configure master node 

search kubernetes instal with kubeadm

1) swapoff -a
2) dnf instll -y iproute-tc
3) modprobe overlay -> is is  a kernal module for network overlay
4) modeprobe br_netfilter -> is also a krnal module or driver for pating in network
5) cat <<EOF | sudo tee /etc/modules-load.d/k8s.conf -> for permenant drivers , in system
		overlay
		 br_netfileter
		 EOF
	WE NEED TO ENABLE IP FORWORING 
6) CAT <<EOF | sudo tee /etc/sysctl.d/k8s.conf
		net.bridge.bridge-nf-call-iptables systemctl enable --now kubelet = 1
		net.ipv4.ip_forward                 = 1
		net.bridge.bridge-nf-call-ip6tables = 1
		EOF
7) sysctl --system


8) setenforce 0 -> seLinux stop
9) cat << EOF | tee /etc/yum.repo.d/cri-o.repo
		[kubernetes]
		name=Kubernetes
		baseurl=https://pkgs.k8s.io/core:/stable:/$KUBERNETES_VERSION/rpm/
		enabled=1
		gpgcheck=1
		gpgkey=https://pkgs.k8s.io/core:/stable:/$KUBERNETES_VERSION/rpm/repodata/repomd.xml.key
		EOF
10) cat <<EOF | tee /etc/yum.repos.d/cri-o.repo
		[cri-o]
		name=CRI-O
		baseurl=https://pkgs.k8s.io/addons:/cri-o:/$PROJECT_PATH/rpm/
		enabled=1
		gpgcheck=1
		gpgkey=https://pkgs.k8s.io/addons:/cri-o:/$PROJECT_PATH/rpm/repodata/repomd.xml.key
		EOF
11) dnf install -y cri-o kubelet kubeadm kubectl
12) systemctl enable --now crio
13) systemctl enable --now kubelet
14) Install crioctl 
15) Install kubeadm tool
16) kubeadm init -help
17) use 192.168.0.0/16 cidr 
18) kubeadm init --pod-network-cidr=192.168.0.0/16
19) kubectl get pods -n kube-system
20) kubeclt create deployment myd1 --image=vimal13/apache-webserver-php
21) kubectl taint nodes --all node-role.kubernetes.io/control-plane-
======================================================
22) kubeadm join -help
23) kubectl token create --print-join-command -> run it on control plane
24) kubectl label node <hostname> <setlablenamehere>

========================================================
25) kubectl get --raw=`/readyz?verbose`
26) kubectl scale deployment myd1 --replicas=5
=======================================================
setup network to use k8s as networking tool , not to use docker or podmand or crio networking tool / setup overlay

cd /etc/cni/net.d/  -> networking file of crio

we need to tell the crio that don't manage networking let k8s handle all the networking things


kubectl delete all --all

Install calico

curl https://raw.githubusercontent.com/projectcalico/calico/master/manifests/calico.yaml
it will download a calico.yaml file 


# Auto-detect the BGP IP address.  (BACKGROUPND GATWAY PROTOCOL)
            - name: IP
              value: "autodetect"
            - name: IP_AUTODETECTION_METHOD
              value: "interface=eth0"

kubectl apply -f calico.yaml

install metrics server 
run these two command on control plane

kubectl apply -f https://raw.githubusercontent.com/techiescamp/kubeadm-scripts/main/manifests/metrics-server.yaml
kubectl top nodes


===============================================
expose the deployment

============================
setup kubectl on client 

cd /etc/kubernetes/ -> admin.conf

in mykueset.txt replace , private ip to public ip   server: http://ip:port

kubectl get pods -kubeconfig mykubeset.txt

kubectl get pods -kubeconfig mykubeset.txt --insecure-skip-tls-verify -> for bypass encription par ip bases


