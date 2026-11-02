# Excessive trust in client-side controls
In this, the server does not validate client side POST request aand we have to exploit this vulnerability to place order.

## Approach

* First, add to cart a Lightweight l33t leather jacket but when you try to place the order, you will see not enough credits.
* Now, go into Burp Suite HTTP history and check for a POST method for cart.
* Ssend the POST method to Repeater.
* In the repeater, you will notice a variable named price. Change it to something lower than the store credits and send the request.
* Then check teh cart and you will see that the price of the item has been lowered and now you can place the order and so the lab is solved.