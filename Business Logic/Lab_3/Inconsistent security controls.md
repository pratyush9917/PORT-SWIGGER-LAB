# Inconsistent security controls
In this, there is no restriction to change the domain of your email to teh domain of company employees after registration.

## Approach

* First, we have to find the domain of company employee email.
* Go to Target tab in Burp, tehn find the domain of the lab. Right click on it an and select Engagement tool and open discover content.
* In discover content, click session not running to start the session and open teh site map tab in the discover content.
* After sometime, a /admin GET request will appear. Open it in browser and you will see admin panel only for dontwannacry user. This is company domain.
* Now, register normally using teh email provided in the email client.
* After registering, change your email domain to @dontwannacry.com.
* After it is updated, an admin panel will show up. Inside that, deelete user carlos to solve the lab.