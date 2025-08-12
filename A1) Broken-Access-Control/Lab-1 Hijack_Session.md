
**Hijack_Session**                                                                                    
**Concept**
Application developers who develop their own session IDs frequently forget to incorporate the complexity and randomness necessary for security. If the user specific session ID is not complex and random, then the application is highly susceptible to session-based brute force attacks.

**Goals**
Gain access to an authenticated session belonging to someone else.0

in this lesson we are trying to predict the 'hijack cookie' value. The 'hijack cookie' is used to differentiate authenticated and anonymous users of WebGoat.

- Log in to the OWASP Goat Web application and select Lab-1: Hijack Session.
![alt text](<../image/Lab-1 Hijack_Session.md/image-1.png>)


- You will see a login form with Username and Password text fields. Now, intercept this request using Burp Suite




- Now send this request to Repeater and remove hijack session cookie from Request and send it again to generate new session cookie


-In Repeater, click the Send button twice to generate multiple sessions (double hijack cookie) and observe the pattern. We found that there is a gap of 2 in the session numbers.


- Now copy the new session cookie and paste it on Request body and sent this request to intruder 


- Now, modify the Intruder request by targeting the session cookie and timestamp parameters.
- Set the payload type to Number, and define the payload range from 6244 to 9080, because the original payload is: 1209030689935531689-175416434§6244§. And Click on Start to do the brute force attack







