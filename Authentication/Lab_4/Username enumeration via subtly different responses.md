# Username enumeration via subtly different responses

In this lab, we have to crack the username and password using subtly different response received from the server.

## Approach

* In the lab, login using any username and password.
* Send the POST of login to intruder
* In Intruder, select username as payload and paste the payloads given in the lab there and select sniper lab.
* Before starting the attack, go to settings tab.
* In settings tab, find Grep Extract. 
* In Grep extract, click add and in the tab that opens, cliks fetch response. There, find and select the Invalid username or password, and click enter.
* Now, start the attack. In the results, there is another column, warning. Sort that. There, a different response for the correct username is shown. Send that payload to the intruder and this time, make password the payload and attack on it.
* One of the passwords for that username will show 302 code. That will be the username and password.