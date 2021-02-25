**Strategies for deploying Machine Learning Inferences models using Lambda**

There is more than one way to deploy a machine learning inference model using Lambda. Lambda is serverless and the Pay as you go option helps to address burst workload with no overhead of running or managing the infrastructure. Depending on the kind of workload and the use case, one of these options can be used.

**1.Inference Model packaged along with Lambda** 

Small models that can be packaged for small inference use cases. Tensor Flow Lite and few other models can be used here. 
![Lambda Machine Learning Use-Cases-2.png]({{site.baseurl}}/Lambda Machine Learning Use-Cases-2.png)



**When to use **

Prototyping, small models used in mobile apps or devices that has constraints with resources  

**Pros**

Simple and easy to use

**Cons**

Models are usually large and cannot be packaged as part of Lambda using this approach  
Continuous updates to the model mean re-deployment of lambda. There is no de-coupling of Lambda and Model 

**Reference**

https://segments.ai/blog/pytorch-on-lambda


2.Inference Model packaged as Lamba layers 

Here the Inference model is packaged as part of  Lambda layers.  



When to use 

Model re-usability across different use cases. 

Pros

     1.Simple and easy to use
     2. Lambda and Model are separately packaged even though the change in the model means re-deployment of lambda layers and in turn Lambda itself
Changes to the model can be updated in the layers alone and all Lambdas that are referencing the layers are automatically updated with the new updated model

Cons

      1. Models are usually large and cannot be packaged as part of Lambda
      2. Continous updates to the model mean re-deployment of lambda. There is no de-coupling of Lambda and Model 
Lambda has a limitation of only 5 layers. This could be challenging. 

Reference: 

https://towardsdatascience.com/aws-lambda-amazon-api-gateway-not-as-daunting-as-they-sound-part-1-d77b92f53626


3.Inference Model loaded from S3 to  Lambda 

Here the Inference model is available in S3 and Lambda downloads the model for execution 



When to use 

Pros

     1.Simple and easy to use
     2. Lambda and Model are decoupled. Inference Models can be continuously updated with no need for a separate lambda deployment. 

Cons

      1. Models are usually large and loading the complete model into Lambda for processing may take a really long time. 
      2. Larger models cannot be loaded into Lambda 

Reference https://towardsdatascience.com/deploying-sklearn-machine-learning-on-aws-lambda-with-sam-8cc69ee04f47


4.Lambda invoking Inference Model Endpoint available  Sage Maker

Sagemaker is used for Machine Learning. It provides both training and inference model endpoints. Lambda can call the inference model endpoint available in Sage Maker. Calling an Inference model in SageMaker is just another API invocation and SageMaker by itself has no connection to Lambda whatsoever. But this is yet another pattern followed in case there are pre-processing or post-processing logic required based on the inference model response  

When to use 

If Sagemaker is already available for Model training, the inference is an additional step. It is always better to leverage the SageMaker Model Inference endpoint. 



Pros

     1.Simple and easy to use
     2. Lambda and Model are decoupled. Inference Models can be continuously updated with no need for separate lambda deployment. 

Cons

      1. Not part of typical Lambda use case
      2. Scaling and other challenges associated with the SageMaker Inference endpoint need to be addressed. 
      3. SageMaker inference endpoints may not be serverless.

Reference https://levelup.gitconnected.com/deploy-your-machine-learning-model-as-a-rest-api-on-aws-english-dcb1a0db3110
 

5.Lambda invoking Inference Model available in EFS 

This is one of the newest approaches available. EFS can be used to both train and deploy models. EFS can also be mounted on the Lambda as an extension. This ensures that Model training and deployment into production can happen with no impact on Lambda deployment. Also, the cold start issue typically associated with loading a large model from S3 or other packages restriction can be greatly avoided. 



When to use 

Pros

     1 . Lambda and Model are decoupled. Inference Models can be continuously updated with no need for separate lambda deployment. 
     2. EFS can scale really well. 
     3. No cold start issues as the model downloading is not required here.  
      
Cons
    
Setup is slightly complex with the setting up of EFS and endpoints. 
EFS is not serverless? Need to pay for the services of EFS  irrespective of its usage 

Reference

https://medium.com/faun/setup-serverless-ml-inference-with-aws-lambda-efs-738546fa2e03

https://thenewstack.io/tutorial-host-a-serverless-ml-inference-api-with-aws-lambda-and-amazon-efs/


6.Lambda and Inference Model packages as Lambda Containers 



This is the most recently available option. Lambda and Model Inference can be packaged as a single container, pushed to ECR and then Lambda can use a container repository URI to load the packages 


When to use 

Pros
     
     1. Fits the usual Lambda and serverless pattern 

Cons

    
Setup is slightly complex with the setting up of EFS and endpoints. Need to use Docker files. 
Packaging allowed is up to a size of 10 GB only. Inference Models that are larger than this size cannot use this approach. 

Reference: 

https://aws.amazon.com/blogs/machine-learning/using-container-images-to-run-pytorch-models-in-aws-lambda/


These are some of the various approaches that can be used to run Model Inference use-cases in Lambda. Please let us know if there any other approaches widely used that is missed out here? 


References 



















Lambda Machine Learning  Inference Model Deployment Matrix  

Sl.No
Strategies
Ease of Packaging/
Deployment
Performance


Lambda - Model Decoupled
Suitable for  Large Models
1
Models packaged along with Lambda 
Easy
Cold Start problems exist 
No
No
2
Models packaged along with Lambda as Lambda layers 
Medium 
Cold Start problems exist 
No
Up to 5 lambda layers 
3
Models packaged along with Lambda using Lambda Container Packaging 
Medium
Cold Start problems exist 
No
Up to 10 GB
4
Models available in S3 and downloaded into Lambda during execution
Easy
Cold Start problems exist 
Yes
Yes
5
Model Endpoint in Sage Maker and lambda invoking the Sage Maker Model Inference Endpoint
Easy
Good
Yes
Yes
6
Model deployed in EFS and mounted in Lambda as an extension
Easy
Cold Start problems exist 
Yes
Yes


