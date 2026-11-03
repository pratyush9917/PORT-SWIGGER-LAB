# Inconsistent handling of exceptional input
In this, we have to use the maximum length of the email address to trick the server into believing we are an admin user

## Approach

* First, try to register using your own email provided in email client.
* Then, open the POST /register request in repeater. Notice that the @ symbol is replaced with %40
* Now, make attacker in the email into a paylaod, change the type to character blocks, base string A, min length 100, max length 500 and step 100 and run the attack.
* Within the email client, you will notice 5 emails for the same account registration. Click teh one with the longest name and login to the account
* After logging in, you will notice only a part of the email is shown and on finding the length, you will notice the length to be 255.
* So, we will change the email so that the end contains our email but the starting 255 characters will display the company email.
* To find the company email, use the method shown in Lab 3 of Business logic.
* Now, we insert the 255 characters instead of attacker in a new request for user registration
* Remove enough characters from the characters so that the @dontwannacry.com is the last character in the email so that when server takes the email, upto 'm' in com is uploaded to the server
* Make sure the email is of the format
  ```text
  very-long-string%40dontwannacry.com.exploit-{your specific code in email}.exploit-server.net```
* Make sure you count %40 as one single character and send the request.
* Open your email client and you will see a confirmation mail for the specific email you entered and open the link.
* Now, log in to your account and see the email. If there are extra or less characters, then make a new request for account registration and adjust the length accordingly.
* If the email is correct, you will see an admin panel.
* Go into the admin panel and delete user carlos to complete the lab.