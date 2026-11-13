# Authentication bypass via flawed state machine
In this, the developer has made the assumption that the events happen in a sequence and did not reinforce the sequence checking.

## Approach

* First, login using the given credentials and note the sequence of events as they happen.
* Now, use the discover content tool to find the admin URL and try to open it. You will be denied.
* Now, logout and go to the login page.
* In Burp, turn on intercept and then login.
* Forward the login, and the next request will be for role selection. Drop this request.
* On dropping the request, the page will show an error. In the URL, remove the role-selector from it and enter and turn of intercept for this.
* Now, you will notice an admin panel. Open it and delete user carlos to solve the lab