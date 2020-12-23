# Terraform AWS VPC Tutorial (Create AWS VPC for EKS cluster with DNS support) Ep 1

- Add Kubeconfig
```bash
$ aws eks --region us-east-1 update-kubeconfig --name eks
```

➜  terraform git:(main) ✗ kubectl get svc
error: You must be logged in to the server (Unauthorized)

aws --profile terraform sts get-caller-identity

aws --profile terraform eks update-kubeconfig --name eks --region us-east-1

kubectl config view --minify

kubectl edit configmap aws-auth -n kube-system

   mapUsers: |
    - userarn: arn:aws:iam::424432388155:user/aputra
      username: aputra
      groups:
        - system:masters