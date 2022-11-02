# Localstack

[Read the docs](https://docs.localstack.cloud)


CRUD: The service accepts requests and returns proper (potentially static) responses. No additional business logic
besides storing entities.
Emulated: The service imitates the functionality, including synchronous and asynchronous business logic operating
on service entities.

https://docs.localstack.cloud/integrations/


## Instalando o Localstack
```
python -m pip install localstack
```

## Rodando o Localstack

### Opção 1 - No python
```
localstack start
```

## Opção 2 -  No docker
```
docker run --rm -it -p 4566:4566 -p 4571:4571 localstack/localstack
```

# Using AWS CLI

## AWSLocal wrapper (Option #1)
```
pip install awslocal-cli
awslocal s3api list-buckets --region us-east-1
```

## AWS CLI pointing to endpoint (Option #2)
```
aws --endpoint-url=http://localhost:4566 s3api create-bucket --bucket my-bucket --region us-east-1
```

