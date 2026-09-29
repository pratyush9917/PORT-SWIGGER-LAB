# 2FA Broken Logic

In this lab, we have to login to carlos' account without using the password and breaking through the 2 Factor Authentication

## Approach

* First login using the given username and password and use the email client for the code and login.
* In burp suite, find the POST login2 history, and send it to intruder.
* There, change the value of verify to the victim's username and make the mfa-code value into a payload.
* In the payload section, change the type to Brute Forcer, make the character set from 0 to 9, min and max length 4 and start the attack.
* In the response tab, while the attack is running, keep sorting the status code until one of payloads results in code 302. 
* At this point, pause the attack, send the request to repeater, and in repeater, open the request in new browser session and you have just logged into the victim's account.