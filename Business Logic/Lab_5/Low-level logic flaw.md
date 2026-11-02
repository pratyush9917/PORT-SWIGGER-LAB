# Low-level logic flaw
In this lab, we have to exploit the quantity value so it becomes negative.

## Approach

* First, try to place an order for a single jacket to register the POST request in Burp.
* Now, find the POST /cart request and send it to repeater.
* In repeater, you will find that only 2 digit value of quanity is accepted.
* So, make quantity into 99 and send the request to intruder.
* In intruder, clear all payloads, set the payload type to null and continue indefinitely and in resource pool, set maximum concurrent request to 1 and start the attack.
* After some time, you will notice ethat despite the high quantity, the total price has become a negative value. This is because the highest value, 2 million, was exceeded and so the value reset to negative.
* Now, clear the cart and go back to the same request with same conigurations but this time, set 323 payloads.
* After attack is finished, send a single request through repeater for 47 jackets and this will bring the net total to $1221.9
* Now, select some other item and keep incresing their value until the net price is somewhere between 0 and 100 dollars and place the order to solve the lab.