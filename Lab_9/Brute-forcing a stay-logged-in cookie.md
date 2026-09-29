# Brute-forcing a stay-logged-in cookie

In this lab, we have to exploit the stay logged in cookie to gain access to the account

## Approach

* First, login using the given credentials and also check the stay logged in check-box
* In Burp Suite, find the GET login request. Send it to repeater.
* There, a cookie for stay-logged-in will appear. Send that cookie to decoder.
* In decoder, decoding it will provide the username followed by a long code separated with a colon. Copy that code and decode it in any hash decoder and it will give the password for that username.
* In the repeater, send the request to Intruder.
* In Intruder, make the stay logged in cookie into a payload and paste all the passwords
* Scroll down, and within Payload processing, add the following rules in the exact order
  * Hash: MD5
  * Add Prefix: carlos:
  * Base64-encode
* Now, change the id value at the top to carlos and start the attack.
* In the responses, all the attacks should result in 302 code. Pick any and open in new browser session and lab is solved.