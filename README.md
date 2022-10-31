# Serverless-Application-in-AWS

<h1>Application architecture</h1>
Architechture of the <b>Serverless Application </b>

![serverless architechture  yeshwanth](https://user-images.githubusercontent.com/94180456/199057712-32bb4529-50a2-4c0f-b4b7-5bd70f48c2de.jpg)

<h2>Application architecture</h2>
The application architecture uses AWS Lambda, Amazon API Gateway, Amazon DynamoDB, Amazon Cognito, and AWS Amplify Console. Amplify Console provides continuous deployment and hosting of the static web resources including HTML, CSS, JavaScript, and image files which are loaded in the user's browser. JavaScript executed in the browser sends and receives data from a public backend API built using Lambda and API Gateway. Amazon Cognito provides user management and authentication functions to secure the backend API. Finally, DynamoDB provides a persistence layer where data can be stored by the API's Lambda function.

