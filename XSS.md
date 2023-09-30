
<h1>Cross-Site Scripting Testing (XSS)</h1>
<h2>Steps</h2>


  Two types of XSS:<br>
  (Will be doing a manual scan)
  <br><br>

  
- Reflected XSS
  <br>
- Stored XSS

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
**CONCLUSION**: This method is called brut force password login with the help of burpe suite, it concludes that we can log in into accounts if there passwords are weak and easily hacked.

  

<br>
<h2>Reflected XSS</h2>
<br>
<p><b>Description:</b> Cross-site scripting (XSS) is an injection attack where a malicious actor injects code into a trusted website. Attackers use web apps to send malicious scripts to different end-users, usually from the browser side. Vulnerabilities that enable XSS attacks are common. They occur wherever web applications use unvalidated or unencoded user-supplied inputs.</p>


- Visit BurpSuite Lab on: <br>
  https://portswigger.net/web-security/cross-site-scripting/reflected/lab-html-context-nothing-encoded


- Create an account to access the contents
- Open Burp Browser. It serves as a Proxy Browser

- Now, in BurpSuite, toggle on 'Inercept on' in Proxy>Intercept
- Open the lab link mentioned above and search 'HI'
- Now in Intercept(Burpsuite) press Forward and then toggle off Intercept
- Noitce in Proxy > HTTP History, the link appears with all the logs
- Right-click on the link> Send to Repeater
- In Repeater, you'll notice the text you've inputed 'HI'
- Now, try changing the HI --> <script>alert('HEYYY')</script>. It will give a prompt of 'HEYYY' on the website


<br>
<h2>Saved XSS</h2>
<br>

- Open the same lab
- Open Burp Browser. It serves as a Proxy Browser

- Now, in BurpSuite, toggle on 'Inercept on' in Proxy>Intercept
- Open the lab link mentioned above, select a post, Feed data: Comment, Name, Email, Website
- Now in Intercept(Burpsuite) press Forward and then toggle off Intercept
- Noitce in Proxy > HTTP History, the link appears with all the logs
- Right-click on the link> Send to Repeater
- In Repeater, you will see the comment response, change the response to <script>alert(0)</script>
- Now whenever a user, clicks on that partciular section, it will be redirected to a vulnerable website: https://vulnerable-website.com



