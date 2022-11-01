# Serverless-Application-in-AWS

<h1>Application architecture</h1>
Architechture of the <b>Serverless Application </b>

![serverless architechture  yeshwanth](https://user-images.githubusercontent.com/94180456/199057712-32bb4529-50a2-4c0f-b4b7-5bd70f48c2de.jpg)

<h2>Application architecture</h2>
The application architecture uses AWS Lambda, Amazon API Gateway, Amazon DynamoDB, Amazon Cognito, and AWS Amplify Console. Amplify Console provides continuous deployment and hosting of the static web resources including HTML, CSS, JavaScript, and image files which are loaded in the user's browser. JavaScript executed in the browser sends and receives data from a public backend API built using Lambda and API Gateway. Amazon Cognito provides user management and authentication functions to secure the backend API. Finally, DynamoDB provides a persistence layer where data can be stored by the API's Lambda function.

<h1>1) Host a website using <b>AWS Amplify </b></h1>

At first the codes are uploaded in my repository you can clone my github repo or download the files.Then by using GIT you can either push the code in AWS codecommit or Github.Then you will configure our AWS Amplify for our web hosting.

In this module, you'll configure AWS Amplify to host the static resources for your web application with continuous deployment built in. The Amplify Console provides a git-based workflow for continuous deployment and hosting of full-stack web apps. In subsequent modules, you'll add dynamic functionality to these pages using JavaScript to call remote RESTful APIs built with AWS Lambda and Amazon API Gateway.The architecture for this module is very straightforward. All of your static web content including HTML, CSS, JavaScript, images, and other files will be managed by AWS Amplify Console. Your end users will then access your site using the public website URL exposed by AWS Amplify Console. You don't need to run any web servers or use other services to make your site available.
refer my repositories for the code

<h1>2) Authenticate users using AWS API Gateway </h1>

When users visit your website they will first register a new user account. For the purposes of this workshop we'll only require them to provide an email address and password to register. However, you can configure Amazon Cognito to require additional attributes in your own applications.

After users submit their registration, Amazon Cognito will send a confirmation email with a verification code to the address they provided. To confirm their account, users will return to your site and enter their email address and the verification code they received. You can also confirm user accounts using the Amazon Cognito console with a fake email addresses for testing.

After users have a confirmed account (either using the email verification process or a manual confirmation through the console), they will be able to sign in. When users sign in, they enter their username (or email) and password. A JavaScript function then communicates with Amazon Cognito, authenticates using the Secure Remote Password protocol (SRP), and receives back a set of JSON Web Tokens (JWT). The JWTs contain claims about the identity of the user and will be used in the next module to authenticate against the RESTful API you build with Amazon API Gateway

<h1>3) Serverless Lamda Backend </h1>
In this module, you will use AWS Lambda and Amazon DynamoDB to build a backend process for handling requests for your web application. The browser application that you deployed in the first module allows users to request that a unicorn be sent to a location of their choice. To fulfill those requests, the JavaScript running in the browser will need to invoke a service running in the cloud.

You will implement a Lambda function that will be invoked each time a user requests a unicorn. The function will select a unicorn from the fleet, record the request in a DynamoDB table, and then respond to the frontend application with details about the unicorn being dispatched.

The function is invoked from the browser using Amazon API Gateway. You'll implement that connection in the next module. For this module, you will just test your function in isolation.
 
<h1>4) Deploy a RESTful API </h1>
In this module, you will use Amazon API Gateway to expose the Lambda function you built in the previous module as a RESTful API. This API will be accessible on the public Internet. It will be secured using the Amazon Cognito user pool you created in the previous module. Using this configuration, you will then turn your statically hosted website into a dynamic web application by adding client-side JavaScript that makes AJAX calls to the exposed APIs.

The static website you deployed in the first module already has a page configured to interact with the API you will build in this module. The page at /ride.html has a simple map-based interface for requesting a unicorn ride. After authenticating using the /signin.html page, your users will be able to select their pickup location by clicking a point on the map and then requesting a ride by choosing the "Request Unicorn" button in the upper right corner.

This module will focus on the steps required to build the cloud components of the API, but if you're interested in how the browser code works that calls this API, you can inspect the ride.js file of the website. In this case, the application uses jQuery's ajax() method to make the remote request.
