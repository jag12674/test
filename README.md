# test
test contains 2 solutions and 1 postman collection

The test was developed on VisualStudio using C# and VB.

First solution is named WebApplication and its in 6 parts. This is the API Server, its in C#. The definition of the methods is in the ServerController.cs file. To validate that the signature matches the one expected, the method GrantResourceOwnerCredentials in the file AppOAuthProvider.cs, create this value string.Format("grant_type:password;key:{0};route:{1}", key, route), after the string is created, it was encrypted using HMACSHA256 and the result is compared with the signature sent as parameter when the tokes its acquired.

Second solution is named WindowsApplication. This is the Client, its in VB. The app.config file contains the application settings included key, shared_key, route and signature that are used in the PUT, POST and GET methods. The main form is composed on 4 groups, each one for each method.
Each group has the parameters expected and a textbox to display the response.

The postman collection includes the requests for each method created in API Server with the parameters expected.

To run the test, first run the WebApplication, it uses a default port 64098. While the API Server is running you can use the client. First needs to set the credentials with the buttons and the values loaded in the PUT credential group. Second you can add messages using the textbox to input the message and the tags (string contain each tag separated by coma), this uses the POST method to insert a message in the memory array. After create the messages you can get them using the options to find by id or by tag (the method messages/{tag} find the ocurrence of the parameter tag in the tag list in any message).
