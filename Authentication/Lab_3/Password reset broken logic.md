# Password reset broken logic

In this, we have to exploit the forgot password to gain access to the victim's account.

## Approach

* First, click the forgot password button and enter wiener(the given user) and click submit to send the email for password.
* Then, in the email client, locate the latest email recovery link and open it
* There, enter the new password but do not click subkit yet.
* In Burp Suite, turn on Interept and then click  submit. 
* In Burp Suite, take the Post request for the password reset link and send it to repeater.
* In the repeater, change the forgot password token at the start and end to any value but both should be same and chaange the username to the victim's username and send it.
* Now, the password should be reset. Try to login using the victim's username and the changed username.