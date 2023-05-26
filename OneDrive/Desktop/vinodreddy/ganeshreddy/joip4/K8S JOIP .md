### installation off kubernates(k8s)

* KUBETRNATES: kubernates is a greek word which means "helmsman" or "pilot"
* kubernates is an open source container that automates the deployment , scalig of management of containerized applications.
    
*With kubernates you can esaily deploy and manage containerized application across a cluster of  machines scaling them up and down as needed.
* It Rolling out updates and managing stortage and networking.
* It provides a portable and extensible platform for managing containerized workloads and services facilitating both declarative configuration and automachine.
     * it container pods.
     * pods contain containers.
* In kubernates nodes present in odd numbers because it elect a masternode to performe infornt of user.
* If master node become server down then the next node become a master node and it perform like a master node like ther nodes are perform in kubernates.

[preview](/k8s11%20(1).webp) this image show the workloads of pods and there uses. 

```
```
### LETS INSTALL THE KUBERNATES IN VIRTUALMACHINE using AWS/ASURE cloud accounts.

* First need to install docker in vm machine by using
   * curl -fsSL get.docker.com -o get-docker.sh
   * sudo sh get-docker.sh


        # shell script
           * #!/bin/bash
           * sudo curl -fsSL get.docker.com -o get-docker.sh
           * sudo sh get-docker.sh
           * sudo usermod -aG docker ubuntu
           * sudo swapoff -a
           * sudo apt update

### After need to install linunx machine in ubuntu

* tps ca-certificates curl
      #then downlopad google cloud siging key
      * 		sudo curl -fsSLo /etc/apt/keyrings/kubernetes-archive-keyring.gpg https://dl.k8s.io/apt/doc/apt-key.gpgsudo apt-get update
     #then add kubernates api resources
      * echo "deb [signed-by=/etc/apt/keyrings/kubernetes-archive-keyring.gpg] https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list
     #then update the package and install kubectl kubeadm kubelet and hold it
      * sudo apt-get update
        sudo apt-get install -y kubelet kubeadm kubectl
        sudo apt-mark hold kubelet kubeadm kubectl
* upcommands do in all node have you taken 
### then coming commands do in masternod what you taken 
  #just init the node to generate some commands to fix/merge with other node
     
     * kubeadm init --pod-network-cidr "10.244.0.0/16" --cri-socket "unix:///var/run/cri-dockerd.sock
  #Then you exit from root and copy paste the command some commands came from init
   *Need to install docker in ec2 machine by using docker script (manually if you need)
    #download the script by using
      * curl -fsSL https://get.docker.com -o install-docker.sh
     #to verify the script content
      * cat install-docker.sh
     #to run the script
      * sh install-docker.sh --dry-run
     #to run the script or in sudo mode
      * sudo sh install-docker.sh

* After installation installation of docker 
    #get into root mode by using
      * sudo -i
    #After weneed to install go language in linux machine /in root
      * wget https://storage.googleapis.com/golang/getgo/installer_linux
        chmod +x ./installer_linux
        ./installer_linux
        source ~/.bash_profile
     #After need to clone the cri-dockered from github and go to current directory(cd) cri dockred
      * git clone https://github.com/Mirantis/cri-dockerd.git
        cd cri-dockerd        
     #After make a bin cridockred and build go docker language in cridockered
      * mkdir bin 
        go build -o bin/cri-dockerd
     #
      * mkdir -p /usr/local/bin
     #then install root
      * install -o root -g root -m 0755 bin/cri-dockerd /usr/local/bin/cri-dockerd
     #
      * cp -a packaging/systemd/* /etc/systemd/system
     #
      * sed -i -e 's,/usr/bin/cri-dockerd,/usr/local/bin/cri-dockerd,' /etc/systemd/system/cri-docker.service
     #
      * systemctl daemon-reload
        systemctl enable cri-docker.service
        systemctl enable --now cri-docker.socket
     #go to home directory of root 
      * cd ~
     #then need to update and install kubernetes api repository
      * sudo apt-get update
       sudo apt-get install -y apt-transport-ht


#after you need to apply these command to install fannel
 * kubectl apply -f https://github.com/flannel-io/flannel/releases/latest/download/kube-flannel.yml

#after these you need to go workernode and copu some coomands from master and paste it ion wokernode
* kubeadm join 172.31.88.27:6443 --token h642tj.5nyyr9qnz9658cmn \
        --cri-socket unix:///var/run/cri-dockerd.sock \
        --discovery-token-ca-cert-hash sha256:a174700cc44bb27ce69bd2ab392df14049a632612724897e477ddc0fdeb912ac
 * check the master node using
    * kubeadm get pods       

 ```
 ```
 ### here we see the pods strucher
   * apiversion: 
   * kind:
   * metadata:
   * spec:

  



