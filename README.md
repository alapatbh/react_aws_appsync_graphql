#### This project is a small POC for integrating AWS app sync with react.

### Steps to follow for the project setup

1. To Create dynamoDb table
   - aws dynamodb create-table --table-name AppSync-Destinations --attribute-definitions AttributeName=id,      AttributeType=S --key-schema AttributeName=id,KeyType=HASH --provisioned-throughput ReadCapacityUnits=10,WriteCapacityUnits=10
2. For some existing data inside the dynamodb (optional)
   - aws dynamodb batch-write-item --request-items file://Destinations.json
3. Create AppSync API
   - Open the AWS AppSync Console and click Create API. 
   - Choose Build from Scratch and click Start. 
   - Enter a name for your API and click Create
4. On the next screen, scroll down to the "Integrate your app" section and download your aws-exports.js config file. Choose the Javascript tab and click Download Config. You will save this file into your ./src directory later.
5. Setup your data sources. We will be using DynamoDB and Lambda as our data sources
   - On the left pane, Select Data Sources. For the name enter *Destinations*.
   - Select the table you created in the previous step and click Create
