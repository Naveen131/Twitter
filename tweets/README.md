Features:
1.User Registration

2.User Email Verification

3.User Login

4.Password reset with email

5. Tweet Create

6.Retweet

7. Tweet Like

8.User Following



User registration

User email verification

Change password - with password reset email.

View user profile


API Documentation

i. User - Registration Create/ Register a new user.

Endpoint 	: http://127.0.0.1:8000/register/
Request Type 	: POST
Request Params 	: username, email, password, password_2, first_name, last_name

Response Http status codes : HTTP_200_OK or HTTP_400_BAD_REQUEST

ii. User - Email Verification Verify the email inorder to activate the user account.

User will recieve an email on successful registration with the verification_code.

Endpoint 	:  http://127.0.0.1:8000/verify/<verification_code>/
Request Type 	: GET

Response Http status codes : HTTP_200_OK or HTTP_404_NO_CONTENT


iii.User - Login Obtain authentication token given the user credentials.

Endpoint 	: http://127.0.0.1:8000/login/
Request Type 	: POST
Request Params 	: email (or username) and password

Response 	: { "token": <token> }
HTTP status code: HTTP_200_OK or HTTP_400_BAD_REQUEST


iv. User - Request for Password Reset Receive an email with password reset link.

Endpoint 	: http://127.0.0.1/password_reset/<reser_code>
Request Type 	: POST
Request Params 	: email
Request Sample : {"email": "some_email_id@gmail.com"}

HTTP status code: HTTP_200_OK



vi. User - Retrieve Profile Retrieve logged in users profile.

Endpoint 	: http://127.0.0.1/user-profile/
Request Type 	: GET
Request Headers :
	Authorization : Token <token>

HTTP status code: HTTP_200_OK or HTTP_401_UNAUTHORISED

vii.Tweet Create - Tweet Create by a user
Endpoint : http://127.0.0.1/create
Request Type:POST
Request Headers :
	Authorization : Token <token>

viii.Tweet Detail
Endpoint :   http:://1270.0.1/<id>
Request Type:POST
Request Headers :
	Authorization : Token <token>

ix.Tweet like
Endpoint :   http:://1270.0.1/<id>/like
Request Type:POST
Request Headers :
	Authorization : Token <token>


x.Retweet
Endpoint :   http:://1270.0.1/<id>/retweet
Request Type:POST
Request Headers :
	Authorization : Token <token>
