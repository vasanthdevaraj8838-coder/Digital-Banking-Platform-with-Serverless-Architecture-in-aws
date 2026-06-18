# Digital Banking Platform with Serverless Architecture on AWS

## Project Overview

This project demonstrates a Digital Banking Platform built using AWS Serverless services. The platform allows customers to create accounts, transfer funds, and view transaction history through secure APIs.

## Architecture

User → API Gateway → AWS Lambda → DynamoDB

### AWS Services Used

- Amazon API Gateway
- AWS Lambda
- Amazon DynamoDB
- Amazon Cognito
- Amazon S3
- Amazon CloudWatch
- AWS IAM

---

## Features

- Customer Registration
- Bank Account Creation
- Fund Transfer
- Transaction History
- Secure Authentication
- Serverless Infrastructure
- Monitoring and Logging

---

## Architecture Diagram

```
+------------+
|   Client   |
+------------+
       |
       v
+----------------+
| API Gateway    |
+----------------+
       |
       v
+----------------+
| AWS Lambda     |
+----------------+
       |
       v
+----------------+
| DynamoDB       |
+----------------+
```

---

## DynamoDB Tables

### Customers Table

| Attribute | Type |
|------------|------|
| CustomerID | String |
| Name | String |
| Email | String |

### Accounts Table

| Attribute | Type |
|------------|------|
| AccountID | String |
| CustomerID | String |
| Balance | Number |

### Transactions Table

| Attribute | Type |
|------------|------|
| TransactionID | String |
| AccountID | String |
| Amount | Number |
| Type | String |
| Timestamp | String |

---

## Project Structure

```
digital-banking-platform/
│
├── lambda/
│   ├── create-customer/
│   ├── create-account/
│   ├── transfer-funds/
│   └── transaction-history/
│
├── api-gateway/
│
├── docs/
│
└── README.md
```

---

## Step 1: Create DynamoDB Tables

Create the following tables:

### Customers

Partition Key:
```
CustomerID
```

### Accounts

Partition Key:
```
AccountID
```

### Transactions

Partition Key:
```
TransactionID
```

---

## Step 2: Create Lambda Functions

### create-customer

Creates a new customer.

### create-account

Creates a bank account.

### transfer-funds

Transfers money between accounts.

### transaction-history

Retrieves transaction history.

---

## Step 3: Create API Gateway

### API Endpoints

#### Create Customer

```
POST /customer
```

#### Create Account

```
POST /account
```

#### Transfer Funds

```
POST /transfer
```

#### Get Transaction History

```
GET /transactions
```

Deploy the API after creating all methods.

---

## Step 4: Configure Amazon Cognito

Create:

### User Pool

Used for authentication.

### App Client

Used by applications to access APIs.

---

## Step 5: IAM Roles

Create a Lambda Execution Role with:

### Permissions

- AmazonDynamoDBFullAccess
- AWSLambdaBasicExecutionRole
- CloudWatchLogsFullAccess

---

## Sample Request

### Create Customer

```json
{
  "customerId": "CUS1001",
  "name": "John Doe",
  "email": "john@example.com"
}
```

---

### Create Account

```json
{
  "accountId": "ACC1001",
  "customerId": "CUS1001",
  "balance": 10000
}
```

---

### Transfer Funds

```json
{
  "fromAccount": "ACC1001",
  "toAccount": "ACC1002",
  "amount": 500
}
```

---

## Sample Transaction Response

```json
{
  "transactionId": "TXN1001",
  "accountId": "ACC1001",
  "amount": 500,
  "type": "DEBIT",
  "timestamp": "2026-06-13T10:00:00Z"
}
```

---

## Monitoring

Use Amazon CloudWatch to monitor:

- Lambda Logs
- API Gateway Metrics
- Errors
- Invocations
- Performance

---

## Testing

### Create Customer

```
POST /customer
```

### Create Account

```
POST /account
```

### Transfer Funds

```
POST /transfer
```

### Get Transactions

```
GET /transactions
```

Test APIs using:

- Postman
- API Gateway Test Console
- Curl

---

## Expected Results

- Customer data stored in DynamoDB
- Accounts created successfully
- Funds transferred securely
- Transactions stored and retrieved
- Logs visible in CloudWatch

---

## Future Enhancements

- Loan Management
- Credit Card Module
- SMS Notifications
- Email Alerts
- Mobile Banking App
- AI Chatbot Support

---

## Author

Vasanth Devaraj

AWS Serverless Banking Project