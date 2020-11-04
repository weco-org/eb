#Deploy EB

https://medium.com/@waihein/deploying-a-simple-node-js-application-to-elasticbeanstalk-using-cloudformation-in-aws-c19c407fb97c

aws cloudformation package \
--template-file template.yml \
--s3-bucket weco-backend-beanstalk \
--output-template-file template-generated.yml

aws --profile weco cloudformation deploy \
--template-file template-generated.yml \
--stack-name weco-backend-beanstalk \
--parameter-overrides KeyName=weco-backend-beanstalk  \
--capabilities CAPABILITY_IAM

aws --profile weco cloudformation describe-stack-events --stack-name weco-backend-beanstalk

## Create express app
https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/create_deploy_nodejs_express.html
