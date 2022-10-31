# Pen-Testing-Live-Targets

Time spent: 8 hours spent in total

Three versions of the Globitek website are available to you. They are mostly identical. However, each one has been given a different color menu bar—blue, green, red—and each one has been given two different security vulnerabilities.

Given ip address: https://35.184.88.145/ and https://104.198.208.81/

# Green

Username Enumeration: Green had the username enumeration vulnerability 
- The mistake that the developer made was that for the login was unsuccessful would not be bold for the non existent username and it will say class = "failed" which is not similar to blue and red styles.css, but if the username does exist then the Login was unsuccessful will be bold and say class = "failure" which is similar to how blue and red is. 

![userenumeration](https://user-images.githubusercontent.com/58159183/199104967-e9d98fe4-b7b0-475d-ba0b-3a70917176e7.gif)


Cross- Site Scripting Vulnerability
- The green site contact form found in section `/green/public/contact.php` allows javaScript to be submitted and display by users in the `/green/public/staff/feedback/index.php` section. The other colors do not allow this and instead allows user to submit feedback as regular.

- I was able to do this by using 
```HTML
<script>alert('Aujanae found the XSS');</script>
```

![crosssitescripting](https://user-images.githubusercontent.com/58159183/199121349-7ebc4993-9aa2-464e-b841-a14c93fe2227.gif)

# Red

Insecure Direct Object Reference
- The red site is vulnerable to the IDOR because when go to the saleperson section you can edit the value of the GET id to `/red/public/salesperson.php?id= blank` . This will give you Testy McTesterson which is ID 10 and Lazy Lazyman which is ID 11.

![IDOR](https://user-images.githubusercontent.com/58159183/199123048-4496a0c0-0b84-41f5-b548-da7ae374b2f3.gif)

Cross - Site Request Forgery


# Blue
SQL Injection
The blue site is vulnerable to SQL injection in the secion `/blue/public/staff/salespeople/show.php?id=` where the id can be use for the injection. 

By setting the id to `' OR SLEEP(3)=0--'` I was able to do SQL injection. The blue site allows to go to other users or obtain other users information with SQL injection as oppose to the green site that took the user back to the salperson page.

![SQL](https://user-images.githubusercontent.com/58159183/199128468-4d3e08d5-d31d-414f-8a2a-452bb71b7681.gif)



