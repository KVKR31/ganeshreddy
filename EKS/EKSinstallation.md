### EKS installation on linux machine/ubuntu

STEPS :

1 . Need an EC2 instance

* `sudo apt update`


2 .  Need AWSCLI 

* ` curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install `

* `sudo ./aws/install --bin-dir /usr/local/bin --install-dir /usr/local/aws-cli --update`

* `aws --version`

3 . Installation of EKSCTL 

* `curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp`

* `sudo mv /tmp/eksctl /usr/local/bin`

* `eksctl version`

4 . Download are install Kubectl

* `curl -LO https://dl.k8s.io/release/v1.23.7/bin/linux/amd64/kubectl`

* `sudo install kubectl /usr/local/bin/kubectl`

* ` kubectl version --client`

5 . Let's configure the AWSCLI configuration like Accesskey,secrete key, loaction etc ..

* `aws configure`
* `AWS Access Key ID [None]: ******`
* `AWS Secret Access Key [None]: ******`
* `Default region name [None]: ****`
* `Default output format [None]: yaml`

6 . Create a vim File using below manifest

```yaml

apiVersion: eksctl.io/v1alpha5
kind: ClusterConfig

metadata:
  name: dev-cluster
  region: us-east-1
  version: "1.23"

vpc:
  cidr: 10.0.0.0/16

managedNodeGroups:
- name: dev-node
  amiFamily: Ubuntu2004
  instanceType: t3.large
  desiredCapacity: 2

```

* Then enter the command to run vim file

`eksctl create cluster -f dev-eks.yml`

7 . Connect the cluster to our nodes using 

`aws eks --region us-east-1 update-kubeconfig --name dev-cluster`

8 . Then check weather nodes are connect to cluster are not

`kubectl get nodes`

9 . Then write a yaml file and apply it

10 . To delete cluster use

`eksctl delete cluster -f dev-eks.yml --wait`

### EKS installation using windows

* `Install awscli`

* `Configure AWS CLi`

* Install EKSCTL on windows using below commands .

`chocolatey install -y eksctl`
`chocolatey upgrade -y eksctl` ### use this command if already installed in your windows...

`eksctl version`

* Then create a folder and write a yamlfile given below then enter the below command to create a cluster...



```yaml     ### cluster.yaml

apiVersion: eksctl.io/v1alpha5
kind: ClusterConfig

metadata:
  name: basic-cluster
  region: eu-north-1

nodeGroups:
  - name: ng-1
    instanceType: m5.large
    desiredCapacity: 10
  - name: ng-2
    instanceType: m5.xlarge
    desiredCapacity: 2

```

* `eksctl create cluster -f <clustername.yaml> `
