# Burpsuite_Demo
**WEBSITE SECURITY TESTING**
**STEPS:**

1)To go to the burp suite lab website first and go to access the lab.
  Link:https://portswigger.net/web-security/logic-flaws/examples/lab-logic-flaws-excessive-trust-in-client-side-controls

2)Login on the page
  username:wiener
  password:peter

3)Go to burp suite and click on intercept is on

4)Go to Website again and add something to the cart

![Screenshot 2023-09-29 193628](https://github.com/MagnusNazareth/BurpSuite_Demo/assets/126322540/cf0b9b08-a2c7-48ae-a6f8-e33c6177a654)

5)It will keep loading and send the details to the burp suite.

![Screenshot 2023-09-29 154752](https://github.com/MagnusNazareth/BurpSuite_Demo/assets/126322540/4a65b177-411d-4236-9a98-fd962592dd1d)

6)Change the price

![Screenshot 2023-09-29 154800](https://github.com/MagnusNazareth/BurpSuite_Demo/assets/126322540/6203c895-beaf-4683-851b-2614ac495bb6)

7)Off the intercept and check the cart again

8)It will show you a different price than the original price.

![Screenshot 2023-09-29 154815](https://github.com/MagnusNazareth/BurpSuite_Demo/assets/126322540/00936035-4d0c-4cdf-9b41-dc3909234aad)

9)And now you can order the same thing with a cheap price.

**CONCLUSION**: In this way we can check the website and see if their security is weak and can find faults in it.


**AUTHENTICATION BYPASS LOGIN**

**STEPS**:

1)Go to the website first
LINK: https://portswigger.net/web-security/authentication/other-mechanisms/lab-password-brute-force-via-password-change

2)Login on the page
  username:wiener
  password:peter

3)Go to burp suite and click on intercept is on

3)Go to change password and write the current password and for the new password request write 2 different passwords for the same.

![Screenshot 2023-09-29 160218](https://github.com/MagnusNazareth/BurpSuite_Demo/assets/126322540/40bb65be-6521-464c-8f19-cfff26d03421)

4)Go to burp suite you will get this in the intercept page

![Screenshot 2023-09-29 155223](https://github.com/MagnusNazareth/BurpSuite_Demo/assets/126322540/48df78a6-efe2-4103-9788-cfa1b91cf5a9)

5)Now go to PROXY in that HTTPS and load POST method for my/account/change/password

![Screenshot 2023-09-29 155430](https://github.com/MagnusNazareth/BurpSuite_Demo/assets/126322540/0cd41f9c-4f0f-46a9-b667-006f7572242a)

6)Right click on it and send it to the intruder.

7)Go to intruder and go to positions and change the username to 'carlos'(demo eg id), add $ option to the current password and keep the attack type as sniper.
   
![Screenshot 2023-09-29 155619](https://github.com/MagnusNazareth/BurpSuite_Demo/assets/126322540/a6852ffd-5cc0-47ab-b90c-e8468adfe3fc)

8)Add no.of demo passwords to the payloads.

![Screenshot 2023-09-29 155542](https://github.com/MagnusNazareth/BurpSuite_Demo/assets/126322540/155e4f14-343b-4c71-84b4-aab62438ea60)

9)Go to settings and go to grep match and remove all the data from it and add New passwords added is incorrect.

![Screenshot 2023-09-29 155508](https://github.com/MagnusNazareth/BurpSuite_Demo/assets/126322540/86313027-491e-4e0e-8ea7-801a2523b1e1)

10)Now start the attack you will get the value as '1' if any of the passwords match the 'carlos username.

![Screenshot 2023-09-29 155801](https://github.com/MagnusNazareth/BurpSuite_Demo/assets/126322540/c21c550a-a07e-4c9b-8cb0-703cdcbb6ad2)

11)Now off the intruder and go to the website again and log out of 'wiener' account and add the 'carlos' username and the password you got as the output from the attack.

![Screenshot 2023-09-29 155835](https://github.com/MagnusNazareth/BurpSuite_Demo/assets/126322540/808416e5-65a9-43f9-a723-c8e6e508fae4)

12)Logged in
    
![Screenshot 2023-09-29 155848](https://github.com/MagnusNazareth/BurpSuite_Demo/assets/126322540/195b9ed4-aa07-4829-b68d-e95e233bf7b5)

**CONCLUSION**: This method is called brut force password login with the help of burpe suite, it concludes that we can log in into accounts if there passwords are weak and easily hacked.
