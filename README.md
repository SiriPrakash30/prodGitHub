CI/CD pipeline


create ec2 instance
connect to ec2
install jenkins
connect to jenkins ip:8080 and setup
yum install docker -y
usermod -aG docker jenkins
usermod -aG docker ec2-user
aws configure
access key : xxxxxxxxxxx
secret access key : xxxxxxxxxxxxxxxxxxx


curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"
echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
kubectl version --client


steps to install eksctl
-----------------------------
ARCH=amd64
PLATFORM=$(uname -s)_$ARCH
curl -sLO "https://github.com/eksctl-io/eksctl/releases/latest/download/eksctl_$PLATFORM.tar.gz"
curl -sL "https://github.com/eksctl-io/eksctl/releases/latest/download/eksctl_checksums.txt" | grep $PLATFORM | sha256sum --check
tar -xzf eksctl_$PLATFORM.tar.gz -C /tmp && rm eksctl_$PLATFORM.tar.gz
sudo install -m 0755 /tmp/eksctl /usr/local/bin && rm /tmp/eksctl

install required plugins - pipeline stage view, blue ocean, docker, k8s

yum install git -yum

install maven using global tool config

docker run -itd --name sonarcont -p 9000:9000 sonarqube
docker start sonarcont

rpm -ivh https://github.com/aquasecurity/trivy/releases/download/v0.70.0/trivy_0.70.0_Linux-64bit.rpm
