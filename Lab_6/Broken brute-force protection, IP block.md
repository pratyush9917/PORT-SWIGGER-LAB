# Broken brute-force protection, IP block
In this, we have to crack the victim's password while dealing with IP-block  of 1 minute  every 3 incorrect attempts

## Approach

* First, try to login using any username and password
* Send the request to repeater and try to send the wrong request two more times but after 2 times, our IP is blocked for one minute.
* However, on further experiment, we discover that the counter for IP block resets after each successfull login using wiener peter.
* To overcome this and crack the password, we alternate wiener and carlos such that each appears one hundred times and alternate peter with one password from the given list such that wiener payload aligns with peter and carlos aligns with each of password.
* Now, we start the pitchfork attack and in the result, one of the carlos attack gives 302 code. This is the correct password for carlos.