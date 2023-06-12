# aws configure
AWS Access Key ID [None]: AKIATJQNTRM7I2UOH3R5

AWS Secret Access Key [None]: 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

Default region name [None]: ap-south-1

Default output format [None]: json

# To install or update kubectl

curl -O https://s3.us-west-2.amazonaws.com/amazon-eks/1.23.17/2023-05-11/bin/linux/amd64/kubectl

curl -O https://s3.us-west-2.amazonaws.com/amazon-eks/1.23.17/2023-05-11/bin/linux/amd64/kubectl.sha256

sha256sum -c kubectl.sha256
openssl sha1 -sha256 kubectl
chmod +x ./kubectl
mkdir -p $HOME/bin && cp ./kubectl $HOME/bin/kubectl && export PATH=$HOME/bin:$PATH

echo 'export PATH=$HOME/bin:$PATH' >> ~/.bashrc

# command for EKS cluster setup in kubectl server: 

aws eks --region ap-south-1 describe-cluster --name pc-eks --query cluster.status

aws eks --region ap-south-1 update-kubeconfig --name pc-eks

kubectl get nodes

kubectl get svc
