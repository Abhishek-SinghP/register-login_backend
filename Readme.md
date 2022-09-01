Register / Login Procedures :

Register :

1. FrontEnd will display the input fields that you want to capture   from the user. Name, Age , Salary , dept , emails, password etc.
2. User will be providing the details in the fields , then he will click on submit button or register / signup button.
3. FrontEnd will verify if all the fields are properly filled and correct . - Validating input fields: Regex regex101.com (Form Validation)
4. FrontEnd will be having an API call which will pass this complete data in API to the backend.
5. Validate email if it is already present or not . Now its time to store the details in DB.
   ENCRYPTION : Information like passwords should not  be stored in the db directly . So we will encrypt the password and then only store it .so this encryption   code will be written in controllers .
6. There is  a library known as bcrypt nmp: any text will be converted into a hash value .
7. Once the bcryt has returned you hashed value , then we will store that in DB along with other user details .

ahdsiod@#$%$^anajsjkao8qwyq87798654(0R)           : Hashed Value 

Login :

1. FrontEnd will take data from user , email, username and password .
2. Click on login button , then FrontEnd will call an API from backend and will pass email and password to it .
3. API comes up with different types of error messages ,
  like if email and password is not provided then msg would be "Please provided required details ",
  if emails is not already present in database , the msg would be :
  "Given email is not registered , Please register ".
  Password's hashed value will be created once again and then it will compare it with the one saved in DB .if it returns then home page if not then error msg will be : "Your password is incorrect , please try with correct password. "
4. Backend /login api will provide the token to the frontend . this token will be generated using library named - jsonwebtoken .
5. After receiving this token from Backend , Frontend will store this token in the local storage . and the whatever next api calls has to be made, this token will be passed in the Headers. inside authorization field concatenated with bearer and then token . 
6. Banking Applications: Token Expiration 

* login - It will give you token , it will say that it should expire in 5 mins. 
* contact - after 4 mins - this api user is trying to access by passing token , at this time he will get the response as well from backend.
* user - after 5 mins - since the token will be expired by now , so the error will be sent to Frontend responsiblity would be to send thew user back to login page is such error occurs. error msg would be :session has expired , please re-login.

Authentication :
Authorization : Role Based access

Authentication is used to authenticate someone's identity , whereas authorization is a way to provide permission to someone to access a particular resource .

Authentication is the log in and authorization is the permission .

