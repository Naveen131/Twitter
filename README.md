# Twitter

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
<code>

Endpoint 	: http://127.0.0.1:8000/register/
Request Type 	: POST
Request Params 	: username, email, password, password_2, first_name, last_name

Response Http status codes : HTTP_200_OK or HTTP_400_BAD_REQUEST

</code>

ii. User - Email Verification Verify the email inorder to activate the user account.

User will recieve an email on successful registration with the verification_code.
<code>
Endpoint 	:  http://127.0.0.1:8000/verify/verification_code
Request Type 	: GET

Response Http status codes : HTTP_200_OK or HTTP_404_NO_CONTENT
</code>

iii.User - Login Obtain authentication token given the user credentials.
<code>
Endpoint 	: http://127.0.0.1:8000/login/
Request Type 	: POST
Request Params 	: email (or username) and password
Response 	: { "token": <token> }
HTTP status code: HTTP_200_OK or HTTP_400_BAD_REQUEST

</code>


iv. User - Request for Password Reset Receive an email with password reset link.

<code>
Endpoint 	: http://127.0.0.1/password_reset/reser_code
Request Type 	: POST
Request Params 	: email
Request Sample : {"email": "some_email_id@gmail.com"}

HTTP status code: HTTP_200_OK
</code>



vi. User - Retrieve Profile Retrieve logged in users profile.
<code>
Endpoint 	: http://127.0.0.1/user-profile/
Request Type 	: GET
Request Headers :
	Authorization : Token token

HTTP status code: HTTP_200_OK or HTTP_401_UNAUTHORISED
</code>


vii.Tweet Create - Tweet Create by a user
<code>
Endpoint : http://127.0.0.1/create
Request Type:POST
Request Headers :
	Authorization : Token token
 </code>

viii.Tweet Detail
<code>
Endpoint :   http:://1270.0.1/id
Request Type:POST
Request Headers :
	Authorization : Token <token>
 </code>

ix.Tweet like
<code>
Endpoint :   http:://1270.0.1/id/like
Request Type:POST
Request Headers :
	Authorization : Token <token>
  </code>


x.Retweet
<code>
Endpoint :   http:://1270.0.1/id/retweet
Request Type:POST
Request Headers :
	Authorization : Token <token>
  </code>
  
  
  
  
Run the project Locally
i. Clone the repository.

ii. Go to directory of manage.py and install the requirements.

pip install -r requirements.txt
Note: You may configure the virtual environment if required.

For instructions, click here : https://virtualenv.pypa.io/en/latest/installation/



EMAIL_HOST_USER = '<to_be_filled>'

EMAIL_HOST_PASSWORD = '<to_be_filled>'

DEFAULT_FROM_EMAIL = '<to_be_filled>'
Note: By default, Sqlite3 database is used. You may also use different database in local_settings file if required.

iv. Run migrations

python manage.py migrate


v. Ready to run the server.

python manage.py runserver


Configuration Variables
VERIFICATION_KEY_EXPIRY_DAYS
Validity (in days) of user account activation email. Defaulted to 2

SITE_NAME
Name of Website to be displayed on outgoing emails and elsewhere. Defauled to Tweets

PASSWORD_MIN_LENGTH
A constraint that defines minimum length of password. Defaulted to 8

INVITATION_VALIDITY_DAYS
Validity (in days) of user team invitation email. Defaulted to 7
