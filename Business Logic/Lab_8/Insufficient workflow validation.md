# Insufficient workflow validation
In this, the server does not check whether the order confirmation requst contains the orders in the carat or whether we have enough store credits

## Approach

* First, login using your credentials
* Now, palce an order that can be bought using the given store credits in the account
* In Burp HTTP history, open the POST cart checkout request and GET order confirmation requests. Notice that there is nothing that checks the store credits or the items that are to be ordered.
* Now, add the jacket to the cart, and send the order confirmation page GET request to repeaater and send the request to solve the lab.