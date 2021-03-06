# aws-full-stack-app

Module 1: CREATE WEB APP

1. Create the index.html and ZIP (compress) only the HTML file.
2. Log into the Amplify Console and under Deploy click the orange Get Started button.
3. Select Deploy without Git provider and click the orange Continue button.
4. In the App Name field type GettingStarted and for Environment name type dev.
5. Select the Drag and drop method and click the Choose files button.
6. Select the ZIP file you created and click the orange Save and deploy button.
7. After a few seconds, you should see the message Deployment successfully completed.
8. Click on the link under Domain and your web app will load in a new browser tab and render "Hello World"

Module 2: Build a Serverless Function

1. Create a Lambda function with Python 3.8 as the runtime.
2. Replace the code with under "Function Code" with the code in hello.py file and click Deploy.
3. Click on "Select a test event" -> "Configure test events" and under "Event Name" type HelloWorldTestEvent.
4. Copy and paste the JSON object from object.json file to replace the default one and click on Test to get the following text: "Execution result: succeeded"

Module 3: Link a Serverless Function to a Web App

1. Log into the API Gateway Console and click the orange "Create API" button.
2. Find the REST API box and click the orange "Build" button in it.
3. Under "Choose the protocol," select REST, under "Create new API," select New API.
4. In the "API name" field type in HelloWorldAPI, select "Edge optimized" in the "Endpoint Type" drop-down and click the blue "Create API" button.
5. In the left nav, click on "Resources" under your HelloWorld API.
6. With the "/" resource selected, click "Create Method" from the Action drop-down menu.
7. Select POST from the new drop-down that appears, then click on the checkmark.
8. Select Lambda Function for the integration type, type in HelloWorldFunction into the "Function" field and click the blue "Save" button.
9. With the newly created POST method selected, select "Enable CORS" from the Action drop-down menu.
10. Leave the POST checkbox selected and click the blue "Enable CORS and replace existing CORS headers" button.
11. In the "Actions" drop-down list select "Deploy API."
12. Select "[New Stage]" in the "Deployment stage" drop-down list, enter dev for the "Stage Name", choose "Deploy"
13. Copy and save the URL next to "Invoke URL" (you will need it in Module Five).
14. On the the left nav, click on "Resources" and click on "POST" on right.
15. Click on the small blue lightning bolt, paste the contents of object.json file into the "Request Body" field and click the blue "Test" button.
16. On the right side, you should see a response with Code 200.

Module 4: Create a Data Table

1. Create a DynamoDB table with name HelloWorldDatabase, Primary Key as "ID" and click "Create" button.
2. Copy the table's "Amazon Resource Name (ARN)" from the right hand panel (you will need it later on in this module).
3. Open the IAM Role for the Lambda function and add an inline policy by copy pasting the JSON object from dynamoDB.json file in "JSON" tab.
4. Open the Lambda function and replace the code with the code from LambdaToDB.py file and click Deploy.
5. Click on Test and verify if an entry is created in the dynamoDB table under "Items" tab.

Module 5: Add Interactivity to Your Web App

1. Replace the code in index.html file with the code in index1.html file, save it and zip it.
2. Open the Amplify Console, click on the web app, click the white Choose files button and select the updated ZIP file.
3. When the file is uploaded, a Deployment process will automatically begin. Once you see a green bar, your deployment will be complete.
4. Click on the URL under Domain, fill in your name and click the "Call API" button.
5. You should see a message that starts with "Hello from Lambda" followed by the text you filled in.
6. Verify if an entry is created in the dynamoDB table under "Items" tab with your name.
