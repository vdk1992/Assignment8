# Project 8 - Pentesting Live Targets

Time spent: **X** hours spent in total

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

Vulnerability #1: SQL Injection

![alt text](https://github.com/vdk1992/Assignment8/blob/master/sql%20injection.gif)

Vulnerability #2: Session Hijacking/ Fixation

![alt text](https://github.com/vdk1992/Assignment8/blob/master/session%20hijack.gif)


## Green

Vulnerability #1: Username Enumeration

![alt text](https://github.com/vdk1992/Assignment8/blob/master/username.gif)

Vulnerability #2: Cross-Site Scripting

![alt text](https://github.com/vdk1992/Assignment8/blob/master/cross-site%20scripting.gif)


## Red

Vulnerability #1: Insecure Direct Object Reference

![alt text](https://github.com/vdk1992/Assignment8/blob/master/insecure%20direct%20object%20reference.gif)

Vulnerability #2: Cross Site Request Forgery

![alt text](https://github.com/vdk1992/Assignment8/blob/master/CRSF.gif)


## Notes

Describe any challenges encountered while doing the work:

- The session hijack problem was really challenging for me just because I didn't know about hacktools until dealing with this problem. When I heard about it from a classmate and was able to play around with what it is and what it does, I was then able to progress with the work.  So yeah, by far the biggest challenge was that problem. 

Which attacks were easiest to execute? Which were the most difficult?

- The SQL injection problem was pretty straight-forward so that was easy. The session hijacking attack was the most difficult for me just because of how long and how stressful the thinking process was for me for this problem. 

What is a good rule of thumb which would prevent accidentally username enumeration vulnerabilities like the one created here?

- I think a good rule of thumb here is simply "less is more" in this situation. A simple approach of checking the username and password, to see if they match using an AND statement and reloading a default page if they don't match would work fine here. Very simple, very effective. 

Many SQL Injections use OR as part of the injected code. (For example: ' OR 1=1 --'.) Could AND work just as well in place of OR? (For example: ' AND 1=1 --'.) Why or why not?

- It can be used in some instances but it just would never work as well as OR because OR followed by a true statement instantly converts an SQL query to true - this is a hacker's landmine. AND just doesn't work as well because both statements, the one on the left and whatever true statement you pass have to match. If they don't, there's no attack. Just doesn't do it, we'll stick with OR. 

A stored XSS attack requires patience because it could be stored for months before being triggered. Because of this, what important ingredient would an attacker most likely include in a stored XSS attack script?

- Some kind of alert system that will notify the attacker when the XSS attack has been triggered.

Imagine that one of your classmates is an authorized admin for the site's CMS and you are not. How would you get them to visit the self-submitting, hidden form page you created in Objective #5 (CSRF)?

- I would hide the page as some sort of hidden popup in another webpage that this classmate just needs to click on. Something salacious. 

Compare session hijacking and session fixation. Which attack do you think is easier for an attacker to execute? Why? One of them is much easier to defend against than the other. Which one and why?

- If a website allows session IDs in their URL, a session fixation would be easier to pull off. Fixation would also be easier to defend against using session identifiers that automatically regenerate. 
