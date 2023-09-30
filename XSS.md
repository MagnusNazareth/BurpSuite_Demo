
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


- Visit BurpSuite on: <br>
  [https://portswigger.net/web-security/cross-site-scripting/reflected/lab-html-context-nothing-encoded](https://0acb005f04a9dacf84e95cb3008e003f.web-security-academy.net/)


- Create an account to access the contents
- Open Burp Browser. It serves as a Proxy Browser
  ![image](https://github.com/MagnusNazareth/BurpSuite_Demo/assets/98711492/3d4cf186-05c9-4fb7-a840-9fabb8af073f)


- Now, in BurpSuite, toggle on 'Inercept on' in Proxy>Intercept
- Open the lab link mentioned above and search 'XSS'
  ![Screenshot from 2023-09-30 05-19-22](https://github.com/MagnusNazareth/BurpSuite_Demo/assets/98711492/6604b6a3-bb69-4d1c-be4f-45837569a97f)

- Now in Intercept(Burpsuite) press Forward and then toggle off Intercept
- Noitce in Proxy > HTTP History, the link appears with all the logs
  ![Screenshot from 2023-09-30 00-02-57](https://github.com/MagnusNazareth/BurpSuite_Demo/assets/98711492/da553138-420e-446f-93af-4d3e948e87ec)

- Right-click on the link> Send to Repeater
  ![Screenshot from 2023-09-30 05-20-29](https://github.com/MagnusNazareth/BurpSuite_Demo/assets/98711492/36b57956-6215-48a6-b813-67cc739c3172)

- In Repeater, you'll notice the text you've inputed 'XSS'
- ![Screenshot from 2023-09-30 05-21-06](https://github.com/MagnusNazareth/BurpSuite_Demo/assets/98711492/bda5155a-26d4-45ee-8707-475950199b5e)

- Now, try changing the HI --> <script>alert('Reflected Input')</script>. It will give a prompt of 'HEYYY' on the website
 ![Screenshot from 2023-09-30 05-21-50](https://github.com/MagnusNazareth/BurpSuite_Demo/assets/98711492/5831972b-79d0-4eba-aa2c-bfdb00af83b8)

- Click Send and you will see a Request and a Response Tab
  ![Screenshot from 2023-09-30 05-22-07](https://github.com/MagnusNazareth/BurpSuite_Demo/assets/98711492/6c44e806-1ce6-441b-b069-ea8d926beda6)

- Other Inputs:
  ![Screenshot from 2023-09-30 05-46-22](https://github.com/MagnusNazareth/BurpSuite_Demo/assets/98711492/1ad73448-c41c-49bf-a8ce-3e22f459605f)





<br>
<h2>Stored XSS</h2>
<br>
<p><b>Description: </b> </p>

- Open the same lab
- Open Burp Browser. It serves as a Proxy Browser

- Now, in BurpSuite, toggle on 'Inercept on' in Proxy>Intercept
- Open the lab link mentioned above, select a post, Feed data: Comment, Name, Email, Website
 ![Screenshot from 2023-09-30 05-51-11](https://github.com/MagnusNazareth/BurpSuite_Demo/assets/98711492/8da47fef-0f17-4632-92f4-72fe7cc22044)

- Now in Intercept(Burpsuite) press Forward and then toggle off Intercept
- Notice in Proxy > HTTP History, the link appears with all the logs
  ![Screenshot from 2023-09-30 05-57-52](https://github.com/MagnusNazareth/BurpSuite_Demo/assets/98711492/465a0f15-61f1-436a-9a4d-f30ec0a29cf6)

- Right-click on the link> Send to Repeater
 ![Screenshot from 2023-09-30 05-53-11](https://github.com/MagnusNazareth/BurpSuite_Demo/assets/98711492/0b380cb8-f9fb-4262-9c40-03ec71e967c7)

- In Repeater, you will see the comment response, change the response to <script>alert(0)</script>
![Screenshot from 2023-09-30 05-59-06](https://github.com/MagnusNazareth/BurpSuite_Demo/assets/98711492/2645f1a7-a171-4fd0-85c3-dc9ef9cae420)

- Now whenever a user, clicks on that partciular section, it will be redirected to a vulnerable website: https://vulnerable-website.com
![image](https://github.com/MagnusNazareth/BurpSuite_Demo/assets/98711492/da5147cb-6974-4334-97f8-f30a1a33ccba)




