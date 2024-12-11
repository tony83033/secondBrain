
CCRI -> OCI ()
CR -> container runtime
CRI -> container runtime interface is a protocol

when k8s support of SHIM we use (containerD)

(k8s -> cri -> containerd -> docker Engine)

note -> docker does not fully support OCI thats why if we use docker in k8s we need to add some extra layer called (SHIM)
kubeadm, docker/cri-o   and runtime runc

USER -> POD -> K8S -> CONTAINER -> C.E -> CONTAINER RUNTIME (RUNC /CRUN/KATA)

==================================================================

multinode cluster

etcd -> database 
kube scheduler -> 
kubeproxy -> nexworking
kuecontroler
kubeAPI
kubelet/or agent program -> run on worker node 

==================================================================

SDN (SOFTARE DEFINE NETWORK PROGRAM)-> IT IS SOFTWARE BUT WORK LIKE 

DISTRIBUTED COMPUTED PROGRAM 

We can run SDM in two different computer or node , but from user perseptive it give feal that it is one single program running on one single computer like (LAN) ACTULAY IT call vxlan (virtul extended lan) or overlay network or GRE 

1) flannel 
2) calico
Note -> We can use VPC as overlay network if using AWS
CNI -> (container network interface)