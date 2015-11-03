# [AwareOSU](http://cailinpitt.github.io/AwareOSU/)
Be aware of crimes around the campus area.

# Background
OSU students (well, college students in general) enjoy being safe. Whenever a crime occurs on campus that has a continuing safety threat, OSU sends every student and staff an email briefly explaining the crime. However, OSU doesn't send crime alerts for all crimes that occur *on and around* campus (where many students live). The reality is that we live in a dangerous world, and we want to be aware of what is happening around us.

# Features
Program runs once every day (using a CRON job), webscrapes the [Columbus Police Department's unofficial web report portal](http://www.columbuspolice.org/reports/) and the [OSU Police department's daily log system](http://www.ps.ohio-state.edu/police/daily_log/view.php?date=yesterday), finds the previous days crimes, and emails the list of crimes to a Google Group of users who signed up for the mailing list.

# Great overview. What is the code actually doing?
This Ruby program utilizes three great gems, Mechanize, Nokogiri, and Mail. This program visits the CPD web portal and OSU PD online log system (listed above) using Mechanize, parses the HTML of the search page containing all crimes committed yesterday using Nokogiri, and sends the information out in a HTML table using Mail.

# Images
#### Email from AwareOSU
![Email from AwareOSU](https://raw.githubusercontent.com/CailinPitt/AwareOSU/master/images/fullEmail.PNG)

---

#### Looks good on mobile too
<img src="https://raw.githubusercontent.com/CailinPitt/AwareOSU/master/images/IMG_2862.jpg" alt="Mobile" width="250" height="445"/>

---

#### Say hi to the Raspberry Pi that runs AwareOSU every morning!
![Raspberry Pi](https://raw.githubusercontent.com/CailinPitt/AwareOSU/master/images/pi.png)

# Why are some crimes listed multiple times?
For example:

![Sometimes you may see crimes listed multiple times in a digest](https://raw.githubusercontent.com/CailinPitt/AwareOSU/master/images/repeat.PNG)

This is because some crimes may have multiple victims, as seen on the Columbus Police Department's web portal:
![Multiple crimes](https://raw.githubusercontent.com/CailinPitt/AwareOSU/master/images/repeat1.PNG)

Currently, victim names aren't included in the digest. Even though this is publically accessible information, I'm not sure how comfortable people would feel with names being emailed to the 400+ AwareOSU users.

# What does the shell script do?
My Pi has been having problems staying connected to an ethernet connection. It will say that it has a connection, but in actuality I cannot access the internet. This seems to be a semi-common problem among Pis, and this also causes problems for AwareOSU since it can't access the internet if there isn't a connection. This script resets the ethernet connection every morning one minute before AwareOSU is scheduled to run, ensuring that the Pi has a valid, working internet connection.

# Goals
1. Develop Android App (no current plans for iPhone because it's $100/year to be an iOS developer, poor college student problems)

# How to sign up
Visit the [AwareOSU Google form](http://goo.gl/forms/Oy5kZ4xHbX) to sign-up.

# Milestones
* 10/27/2015 - AwareOSU has 400 users.

* 10/27/2015 - AwareOSU has 300 users.

* 10/27/2015 - AwareOSU has 200 users.

* 10/24/2015 - AwareOSU is now running from a Raspberry Pi! What does this mean? Basically, this means that AwareOSU is just about fully automated. The only thing I do now is add emails to the Google Group of people who have subscribed, and the Pi uses a CRON job to run Aware OSU every morning at 10:15.

* 10/22/2015 - Program now searches and retrieves on-campus crimes, in addition to off-campus crimes. 

* 10/17/2015 - AwareOSU has 100 users.

* 10/17/2015 - Apparently Google only lets users send out a max of 100 emails/day, so the awareosu@gmail.com account got suspended for a day. From now on, I will be using a Google Group to mass email everyone who signed up through the Google Form. For future software engineers: this is why we test every aspect of our code.

# Press
* [Students for Concealed Carry](http://concealedcampus.org/2015/10/students-for-concealed-carry-applauds-student-led-crime-awareness-initiative/)
* [Lantern TV](https://youtu.be/MAaY5FkLQqI?t=1m51s)

# Disclaimer
[Crimes listed on CPD's web portal is not representative of all crimes that have occurred](http://www.columbuspolice.org/reports/About).