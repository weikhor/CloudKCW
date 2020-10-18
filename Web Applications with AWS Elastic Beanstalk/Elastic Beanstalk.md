## Building Scalable Web Applications with AWS Elastic Beanstalk

In this project, I use sample web application from Github and deploy it to production ON AWS. The AWS service Elastic Beanstalk is used to deploy a functioning web application.  

### The process of this project

a) Creating the EC2 instance using SSH. Use this instance to download and manage web application code for Elastic Beanstalk.

![EC2 instance](./image/EC2-instance.png)

b) Initialize the Web appliction git repository. Sample code used for this project `https://us-west-2-aws-training.s3.us-west-2.amazonaws.com/awsu-spl/spl-45/1.4.8.prod/scripts/v1.zip`

c) Initialize the AWS Elastic Beanstalk

```
eb init -i
```

d) Creates an new application environment and deploys an web application. The following command creates the `Elastic Beanstalk` environment in a `VPC` with an `RDS database` instance and `Elastic Load Balancer`. The service role is assumed by `Elastic Beanstalk` to use other AWS services and the instance profile is applied to the instances in your environment and allows them to use the `RDS database` instance

```
eb create --database --vpc.id vpc-0791847b582a0b7f4 --vpc.dbsubnets subnet-077a1a9f6d7823a99,subnet-090a13ae00a0456a8 --vpc.ec2subnets subnet-077a1a9f6d7823a99,subnet-090a13ae00a0456a8 --vpc.elbsubnets subnet-01557d8cc564706fd,subnet-088c7874807cc828c --vpc.elbpublic -db.i db.t3.micro -db.engine mysql --elb-type application --service-role aws-elastic-beanstalk-service-role --instance_profile qls-20109387-e2eb469875f11ff9-AWSBeanstalkEc2Role-1DUIKC5C1FWNV
```

![Auto Scaling](./image/auto-scaling.png)

![EC2 Target Group](./image/EC2-Target-Group.png)

e) Log into `Elastic Beanstalk` application.

![Elastic Beanstalk](./image/ElasticBeanstalkWebApplication.png)

f) Externalizing server side sessions to improve scalability of web application by allowing all the EC2 instances running the web application uniformly. The Amazon `ElastiCache` service is created to improve the performance of web applications by retrieving information from managed in-memory caches.

![Memory cache](./image/memory-cache.png)

g) Web Application Deployment in production

![Web Application](./image/Web-Application.png)







