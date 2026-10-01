# Username enumeration via account lock
In this, we have to find out the victim's username and password  using cluster bombing the username

## Approach

* First, get the POST login method into the intruder
* Then, select the username and make it into a payload. Add another paylload at the end of password but it shouldn't contain any value. Make this second payload into a null type and type 5 in the generate field and select cluster bomb attack.
* Start the attack.
* After the attack, sort the length recceived. One of response will be different. Send that request into intruder and this time do sniper attack on password. But, add a Grep extract in the Too many incorrect attempts field. 
* In the responses of the attack, one of the attacks does not yield any message. Note the password for this.
* Wait a minute to let the account be unlocked.
* Try to login using the password and username found.