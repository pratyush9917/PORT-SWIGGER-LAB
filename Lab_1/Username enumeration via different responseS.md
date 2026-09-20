# Lab : Username enumeration via different response

In this lab, we are provided with a list of usernames and passwords and using Burp Suite, we need to find the correct username and password to login.

## Requirements

To successfully solve this lab, the following things are necessary
* A basic understanding of Burp Suite, like how Proxy works, how repeater works, how intruder works, types of attacks, Payloads, etc.
* FoxyProxy extension should be installed and a new proxy with hostname 127.0.0.7 and Port 8080 should be setup

## Approach

* First, try to login using any random username and password so that the request registers in the HTTP History of Proxy

![alt text](/image.png)

![alt text](/image2.png)

* After the failed login attempt, check HTTP History and a login URL for POST method should appear

![alt text](/image3.png)

* Right click the POST request and send it to repeter
* There, after sending the request again, it shows invalid username, so we have to find a valid username first. So, right click and send it to Intruder
* Inside intruder, select sniper attack, highlight the username value and click add to make it a payload
* Then, make the payload type into a simple list and paste the list of usernames provided

![alt text](/image4.png)

* Now, start the attack. 
* After the attack, look at the length column of the result. It's value will be same for all payloads except one and that one payload is the one with correct username. Now, send that request to the repeater and look at the response received
* This time, it shows Incorrect password. 
* Now, we send this to the Intruder and repeat these same steps for password
* After the attack on password, we will see that one of the payloads resutlts ina 302 status code. Note the value of the passsword for that request and try t login with the username and password we received and our lab is solved