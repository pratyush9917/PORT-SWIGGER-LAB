# Password reset poisoning via middleware

In this lab, we have to exploit the middleware poisoning to change the password for the victim's account and login using the new passwword

## Approach

* First, click the forgot password button and use the given password and send the reset link.
* Within the exploit server, go to the email client to find the reset link but don't open it.
* Now, find the POST forgot password request in Burp Suite and send it to repeater.
* There, add the following before the username
  ```text
  X-Forwarded-Host: YOUR-EXPLOIT-SERVER-LINK```
  Make sure you DO NOT paste the https:// along with the link after the X-Forwarded-Host and send the request.
* Within the exploit server access log, find the temp-forgot-password-token and copy it.
* Now go to the reset link sent to wiener.
* Copy that and paste it in the browser but in that, change the forgot password token to the one copied from the access log and now, enter.
* Chnage the password to whatever you like, enter and now login to the victim's account.