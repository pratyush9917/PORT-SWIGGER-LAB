# Password brute-force via password change
In this, we have to find the password of the victim using the password change error message.

## Approach

* First, login using the given credentials and tinker with the password fields givn. Notice when password is wrong and the two new passwords mismatch, it shows current password is wrong but if the current password is right but the 2 new passwords mismatch, it shows new passwords mismatch. We have to exploit this.
* Try to channge the password but keep the current password right but the new passwords mismatch.
* In Burp, find the POST request of password change and send it to intruder.
* There, change the username to the victim's username and make the current passwword into a payload and paste the given passwords as payloads.
* In settings, add a Grep-Extract for the message New passwords do not match.
* Now, start the attack.
* In the results, one of the payloads give new passwords do not match while all others will give cureent password is incorrect. Note that password and login to the victim's account using that.