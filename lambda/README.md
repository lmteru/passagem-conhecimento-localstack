# Criação de Lambda Hello-World

![desenho lambda](./assets/aws.drawio.png)

## Criação da role
```
aws --endpoint http://localhost:4566 iam create-role   --role-name lambda-execution  --assume-role-policy-document "{\"Version\": \"2012-10-17\",\"Statement\": [{ \"Effect\": \"Allow\", \"Principal\": {\"Service\": \"lambda.amazonaws.com\"}, \"Action\": \"sts:AssumeRole\"}]}"
```


## Adiciona policy na role
```
aws --endpoint http://localhost:4566 iam attach-role-policy --role-name lambda-execution --policy-arn arn:aws:iam::aws:policy/service-role/AWSLambdaBasicExecutionRole
```

## Cria a função lambda

```
aws --endpoint http://localhost:4566 lambda create-function --function-name HelloWorld --zip-file fileb://hello_world.zip   --handler hello_world.lambda_handler --runtime python3.7 --role arn:aws:iam::000000000000:role/lambda-execution
```


## Chama a função lambda
```
aws --endpoint http://localhost:4566 lambda invoke --function-name HelloWorld out.txt --log-type Tail
```