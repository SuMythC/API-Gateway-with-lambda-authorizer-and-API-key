# API Gateway with Lambda Authorizer and API Key

This project demonstrates how to configure **API Gateway** with a **Lambda authorizer** and **API keys** to authenticate and manage traffic. It also includes **DynamoDB** integration for data management and rate-limiting features using API keys.
![apikey + lambda authorizers](https://github.com/user-attachments/assets/b0a48340-6eaa-4af1-8c40-47b81d6b0c6a)

## Overview

The application leverages several AWS services:
- **AWS Lambda** functions for processing POST and GET requests.
- **API Gateway** for creating RESTful APIs with integrated Lambda authorizers.
- **DynamoDB** for data storage and management.
- **API Keys** for managing access and rate limiting.

The API Gateway is configured to handle:
- **POST** method: For adding records to DynamoDB.
- **GET** method: For retrieving data from DynamoDB.
- **OPTIONS** method: For handling CORS.

---

## Architecture and Setup

### 1. **Lambda Functions**

Three Python **Lambda functions** have been created:
- **Lambda Function for POST**: Adds records to DynamoDB.
- **Lambda Function for GET**: Retrieves records from DynamoDB.
- **Lambda Authorizer**: Authenticates requests before they hit the API Gateway.

#### Lambda Function Screenshots:
- Lambda function:
  ![lambda function](https://github.com/user-attachments/assets/4eeec2af-4780-4ee1-b909-3ea4e27c73c9)
- Lambda authorizer function:
  ![Lambda Authorizer](https://github.com/user-attachments/assets/705a7c16-6c81-4d3f-8d6b-45bcc14d4ca9)
- POST method Lambda function:
  ![Lambda POST](https://github.com/user-attachments/assets/d97be0ed-e133-48d8-898b-989977dc8328)
- GET method Lambda function:
  ![Lambda GET](https://github.com/user-attachments/assets/379cc3aa-728c-4572-84a6-328bc14ed544)

**Note**: Code for each Lambda function is available in the repository. Ensure you assign the correct **DynamoDB access role** to the Lambda functions.

---

### 2. **API Gateway Configuration**

API Gateway is configured to authenticate requests using a **Lambda authorizer** and manage traffic with **API keys**. The API has three methods:
- **POST**: To add records to DynamoDB.
- **GET**: To retrieve records from DynamoDB.
- **OPTIONS**: For CORS handling.

#### API Gateway Screenshots:
- API Gateway configuration:
  ![API Gateway](https://github.com/user-attachments/assets/91235107-998c-41b3-9b9f-83b2cefe25b3)
- API Method setup:
  ![API Method](https://github.com/user-attachments/assets/0a5f898b-f8a5-49fd-a3e2-3ca90a9f0029)

---

### 3. **API Key and Rate Limiting**

API Gateway has been configured to use **API keys** for authentication and managing rate limits. The API key is used to:
- **Authenticate requests**.
- **Set rate limits and quotas** to prevent abuse and ensure fair usage.

#### API Key Screenshots:
- API key configuration:
  ![API Key](https://github.com/user-attachments/assets/c83f1f31-1838-426a-99ec-62260bf7d58a)
- API usage plan:
  ![Usage Plan](https://github.com/user-attachments/assets/0b39e500-0732-48aa-9f67-247f2e9a43f6)
- Lambda authorizer setup:
  ![Authorizer](https://github.com/user-attachments/assets/84a45dc5-6c5b-4087-a0f9-007bfa2829dc)

---

### 4. **DynamoDB Table**

A **DynamoDB table** is created to store the records added via the API. Ensure the table is configured properly for your application.

![DynamoDB Table](https://github.com/user-attachments/assets/484a35c9-bae4-4b63-8e72-d7a4e643e9f5)

---

## Testing

### 1. **POST without API Key**

A **POST** request without an API key results in an unauthorized error.

![POST without key](https://github.com/user-attachments/assets/2aa33194-d624-47d1-a51d-fbb6ebe75e67)

### 2. **POST with API Key**

A **POST** request with a valid API key successfully adds records to DynamoDB.

![POST with key](https://github.com/user-attachments/assets/72e1421d-f984-4272-be27-66913fab84e8)

### 3. **GET without API Key**

A **GET** request without an API key results in an unauthorized error.

![GET without key](https://github.com/user-attachments/assets/dc74b776-7e40-4764-baf7-5875811595fc)

### 4. **GET with API Key**

A **GET** request with a valid API key successfully retrieves records from DynamoDB.

![GET with key](https://github.com/user-attachments/assets/e4a9c1e0-4cc5-4a79-a018-02e3b9ee5832)

---

### 5. **Checking Data in DynamoDB**

Before and after posting data, the state of the DynamoDB table can be checked to confirm that records are being added correctly.

- **Before posting data**:
  ![Before Data](https://github.com/user-attachments/assets/14f35b65-0ad8-4e40-9b6f-f118ff237a24)

- **After posting data**:
  ![After Data](https://github.com/user-attachments/assets/e9d3a583-7a1f-4f07-98f7-03f2f8e3dbb5)

---

### 6. **Both API Key and Authorizer Are Required**

For the API to function properly, **both the API key and Lambda authorizer** are required for authentication.

- **Request without API key**:
  ![Request without API Key](https://github.com/user-attachments/assets/fc22151f-c174-4497-90f5-d7769e28a76d)

- **Request without Lambda Authorizer key**:
  ![Request without Lambda Authorizer](https://github.com/user-attachments/assets/c1882f71-a14c-4351-82c5-75aa23385606)

- **Request with both API key and Lambda authorizer**:
  ![Request with both API key and Lambda Authorizer](https://github.com/user-attachments/assets/76f1947d-517f-473b-b505-40d24ba19e87)

---

### 7. **API Key Exceeds Usage Limit**

If the API usage exceeds the defined rate limit, the API key will be disabled.

![API Key Limit Exceeded](https://github.com/user-attachments/assets/d141b73f-7ec8-4d9d-bd13-249de796877b)
