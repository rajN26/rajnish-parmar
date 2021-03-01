
Objective:  The strategy behind selecting the following test cases for automation was as follows:

1.Applying the User and Business Centric Development, it is important that we make sure that our automated Regression suite contains the test which is important from the business point of view (to get revenue) as well as to make sure that users are able to use the applications main features without any errors.

For example, For ‘user’ API the very most important feature would be Sign Up so that they can put an order for the pets to buy. 

For ‘Store’ API it is important that inventory is up to date so that user gets the correct information

For ‘Pet’ API it is important that new pets can be added or edited as required. 



2.Secondly, API tests should not just focus on the response code verification, it is equally important to test for the quality of data we are receiving and sending. For example, Schema validation for each request.



Following are the proposed test cases for automation:

1.‘User’ API:
2.Verify the user is created successfully.
3.Verify the userList is created successfully.
4.Verify the GET response for ‘/user/{username} follows the defined schema 
5.Verify User is able to login successfully



1.‘Store’ API
2.Verify the GET response for /store/inventory follows the defined schema.
3.Verify the POST response for a Pet Order
4.Verify the GET response for the purchase order by ID.



‘Pet’ API
1.Verify the POST response for adding a new pet.
2.Verify the POST response for a Pet details update

QA Note: There are a couple APIs which are either not clearly documented in terms of expected parameters or not parsing the JSON.


Project Description:

Node.js Framework used are: Mocha, chai, chai-http, chai-json-schema

Instruction: install mocha globally using: npm install mocha

install chai under dev dependencices: npm install chai --save-dev

install chai-http under dev dependencices: npm install chai-http --save-dev

install chai-json-schema under dev dependencices: npm install chai-json-schema --save-dev

install chai-asserttype under dev dependencices: npm install chai-asserttype --save-dev

There are three 3 javascript files i have created:

Project Structure:

In order to understand the application well I have divided the application in three modules: 1.User, 2. Store, 3.Pet.

There are different folders for each module:

1.User  : swagger_UserAPITest
2.Store : swagger_StoreAPITest
3.Pet   : swagger_PetAPITest

Each module folder would have the following files:

1.test.js: this file has all the test cases for api_testing. To ease the maintainability we can sorted out test cases into different folder according to the http requests(GET, POST, DELETE, PUT) or according the system modules

2.*PostData.js : this file will be used as a data repository to store different types of data as per our business requirements and all data call would be happening from this file to test.js

3.*jsonSchema.js: this file will be used as a data repository to store different data schema getting used in our system.

4. Utlity.js : this file would have all the common requests which we might need to perform some specific tasks for example: login User before placing an order.
