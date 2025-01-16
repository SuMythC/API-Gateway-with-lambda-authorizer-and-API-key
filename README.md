# API Gateway with lambda authorizer and API key
![apikey + lambda authorizers](https://github.com/user-attachments/assets/b0a48340-6eaa-4af1-8c40-47b81d6b0c6a)

<strong> Creating three Python lambda functions, each of which is connected to an API Gateway, to manage traffic based on incoming requests: </strong><br>
![lambda function](https://github.com/user-attachments/assets/4eeec2af-4780-4ee1-b909-3ea4e27c73c9)
![lambda authorizer](https://github.com/user-attachments/assets/705a7c16-6c81-4d3f-8d6b-45bcc14d4ca9)
![lambda post](https://github.com/user-attachments/assets/d97be0ed-e133-48d8-898b-989977dc8328)
![lambda GET](https://github.com/user-attachments/assets/379cc3aa-728c-4572-84a6-328bc14ed544)

<strong>Note: code for each lambda is available in th repository. Also give lambda DynamoDB access role.</strong>

<strong> Creating an API Gateway that authenticates requests using a Lambda authorizer and manages quotas and rate limiting through API keys </strong>
![api](https://github.com/user-attachments/assets/91235107-998c-41b3-9b9f-83b2cefe25b3)

<strong> One POST method for adding records to DynamoDB, one GET method for retrieving data from DynamoDB, and one OPTIONS method for handling CORS. </strong>
![api2](https://github.com/user-attachments/assets/0a5f898b-f8a5-49fd-a3e2-3ca90a9f0029)

<strong> API Key and Lambda Authorizer for Authentication with Rate Limiting and Quota Management </strong>
![apikey](https://github.com/user-attachments/assets/c83f1f31-1838-426a-99ec-62260bf7d58a)

![usage plan](https://github.com/user-attachments/assets/0b39e500-0732-48aa-9f67-247f2e9a43f6)
![authorizer](https://github.com/user-attachments/assets/84a45dc5-6c5b-4087-a0f9-007bfa2829dc)

<strong> Creating DynamoDB table </strong>
![dynamodb](https://github.com/user-attachments/assets/484a35c9-bae4-4b63-8e72-d7a4e643e9f5)

# [Testing]
<strong> POST without key </strong>
![post without key](https://github.com/user-attachments/assets/2aa33194-d624-47d1-a51d-fbb6ebe75e67)

<strong> POST with key </strong>
![post with key](https://github.com/user-attachments/assets/72e1421d-f984-4272-be27-66913fab84e8)

<strong> GET without key </strong>
![GET WITHOUT key](https://github.com/user-attachments/assets/dc74b776-7e40-4764-baf7-5875811595fc)

<strong> GET with key </strong>
![get with key](https://github.com/user-attachments/assets/e4a9c1e0-4cc5-4a79-a018-02e3b9ee5832)

# [Checking data in DynamoDB]
<strong> Before posting data</strong>
![dynamodb no data](https://github.com/user-attachments/assets/14f35b65-0ad8-4e40-9b6f-f118ff237a24)

<strong> After posting data </strong>
![dynamodb data](https://github.com/user-attachments/assets/e9d3a583-7a1f-4f07-98f7-03f2f8e3dbb5)

# [Both API key and Authorizer are necessary for your API to work]
<strong> Request without API key </strong>
![request without apikey](https://github.com/user-attachments/assets/fc22151f-c174-4497-90f5-d7769e28a76d)

<strong> Request without Lambda Authorizer key </strong>
![request without lambda authorizer](https://github.com/user-attachments/assets/c1882f71-a14c-4351-82c5-75aa23385606)

<strong> Request with both Lambda Authorizer and API key </strong>
![request with both apikey and lambda authorizer](https://github.com/user-attachments/assets/76f1947d-517f-473b-b505-40d24ba19e87)

# [The API key will be disabled if you exceed the usage limit]
![apikey limit exceeded](https://github.com/user-attachments/assets/d141b73f-7ec8-4d9d-bd13-249de796877b)




