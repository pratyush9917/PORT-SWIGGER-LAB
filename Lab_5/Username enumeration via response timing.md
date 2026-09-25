# Username enumeration via response timing
In this lab, we have to find the victim's username and password while dealing with IP-block

## Approach

*  In the lab, first login using any username and password.
* In Burp Suite, send the POST login request to repeater and change the username and password manually and send it.
* However, after three wrong tries, IP is blocked and we are told to wait 30 minutes.
* To counter this, we first send the request to intruder. There, just before the line containing the username and password, we add a line 
  * X-Forwarded-For: 1

* This time, make this 1 a payload, change the payload to numbers type, from 0 to 100 and make the username another payload and add the payloads and make the password ridiculously long and start a pitchfork attack.
* In the result of attack, check the response timing column. There, the response for the correct username will be very high as compared to the others. Send this request to intruder.
* Again, make X-Forwarded-For: 1 a payload and this time, make password the payload and start another pitchfork attack.
* This time, one request will give 302 code. That will be the correct username and password.