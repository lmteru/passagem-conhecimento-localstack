## Rodando o terraform
```
terraform init
terraform apply
```

# Listando as instâncias EC2
```
aws --endpoint-url=http://localhost:4566 ec2 describe-instances --query 'Reservations[].Instances[].[InstanceId,InstanceType,PublicIpAddress,Tags[?Key==`Name`]| [0].Value]' --output table --region us-east-1
```