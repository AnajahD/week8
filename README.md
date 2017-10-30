# week8
# Project 8 - Pentesting Live Targets

Time spent: **5.5** hours spent in total

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
On the Find the Salesperson tab there is a vulnerability that only occurs on this page. When changing the id number it goes to a certain salesperson information, but 
when I add ' OR SLEEP(5)=0--' to the id then it halts for 5 seconds and then goes back to the first person on the sales page. While in the other target colors
using that command as the id returns the page to the main salesperson page. 
<img src='https://i.imgur.com/JXz6mkb.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />GIF

Vulnerability #2: Session Hijacking/Fixation
Using internet explorer and chrome I was able to do a session hijacking. Having one browser logged in and copy their session id and then put that session id into the other browser.
I could log in to the page without putting a username or password into the login. The other versions of this log you out after 30 minutes so this problem wouldn't occur with them.
<img src='https://i.imgur.com/KZGDemj.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />GIF

## Green

Vulnerability #1: Username Enumeration
The login page of the this version has the username enumeration problem. By testing "jmonroe99" as the username and a random password it shows login unsuccessful in bold for only certain
usernames that actually exist. When I tried "jmonroe" as the username the login error wasn't in bold which meant that username doesn't exist. On the other versions the login error stays
bold the entire time, so doesn't give away which usernames actually exist. 
<img src='https://i.imgur.com/FTC2FMq.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />GIF

Vulnerability #2: Cross-Site Scripting (XSS)
In the Contact tab has the vulnerability of XSS because once you add <script>alert('Anajah found the XSS!');</script> in the feedback box a prompt box will appear once you login in. It will
tell you that you find the XSS and person ok and will show no feedback. In the other versions the script just shows up as text in the feedback 
column, so the other sites are filtering XSS vulnerabilities.
<img src='https://i.imgur.com/ky8PLOK.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />GIF

## Red

Vulnerability #1: Insecure Direct Object Reference (IDOR)
The find a salesperson tab encounters IDOR when an invalid id is put into the url. It still shows the salesperson that doesn't work for the company anymore. The other
versions of the sites just go back to the main salesperon page when and invalid id is presented instead of presenting the hidden information. 
<img src='https://i.imgur.com/22oco5n.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />GIF

Vulnerability #2: Cross-Site Request Forgery (CSRF)
After logging in to the main page. You have the possiblity of editing different users. On the red sight though once you change the value token it still lets you update
the users information. Unlike the other sites that if you change the value token the page gives you an invalid request page because it is actually checking the token here. 
<img src='https://i.imgur.com/f9iQuoY.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />GIF

## Notes

Took some time and trial and error to see what was different in each of the sites since they are similar in appearence. The most difficult vulnerability was the 
session/hijacking one. So that was the last one I did to see which version it narrowed it down to, but overall an intersting project. 
