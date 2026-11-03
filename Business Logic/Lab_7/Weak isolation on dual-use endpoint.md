# Weak isolation on dual-use endpoint
In this, there is no checking for current password for changing the password and only thing checked is username and we have to exploit this vulnerability to delete user carlos

## Approach

* First, login using your credentials provided
* Then, change the password to any paswsord
* In Burp, send the POST change-password request to repeater.
* In repeater, if you remove the current-password entirely and send the request, the request is still successful and the password is changed.
* So, now, change the username to administrator and send the request. The password is successfully changed for aadministrator user.
* Now, login to administrator using the new password.
* In the dashboard, click the admin panel and delete user carlos to solve the lab.