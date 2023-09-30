
<h1>Cross-Site Scripting Testing (XSS)</h1>
<h2>Steps</h2>


  Two types of XSS:<br>
  (Will be doing a manual scan)
  <br><br>

  
- Reflected XSS
  <br>
- Stored XSS



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



