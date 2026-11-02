# Flawed enforcement of business rules
In this, the rule for applying coupon code is flawed which we have to exploit.

## Approach

* First, enter the lab and see that new users are provided with the coupon NEWCUST5.
* Scrolling down to the bottom, we see a space where we can enter an email to receive newsletter. 
* Type in any non existent email and you will receive a new coupon code SIGNUP30.
* Now. add the lightweight jacket to teh cart and apply both coupons.
* Now, when you try to apply the same coupon as last one, it will deny. But, if you alternate between the two coupons, they successfully apply, however many times.
* Keep applying the coupons until the total price is less than the store credits and place the order to solve the lab.