# Aware OSU
-------------------
Be aware of crimes around the campus area.

# Background
-------------------
OSU students (well, college students in general) enjoy being safe. Whenever a crime occures on campus (ex. sexual assult, robbery), OSU sends every student and staff an email breifly explaining the crime. However, OSU doesn't send crime alerts for crimes that occur *around* campus (where many students live). The reality is that we live in a dangerous world, and we want to be aware of what is happening around us.

# Features
-------------------
* Program runs once every day (using a CRON job), webscrapes the [Columbus Police Department's unofficial web report portal](http://www.columbuspolice.org/reports/), finds the previous days crimes, and emails the list of crimes to specified users.

# Goals
-------------------
1. Develop Android App (no current plans for iPhone because it's $100/year to be an iOS developer, poor college student problems)
2. Make this more automatic (I currently have to manually add emails to send information to)
3. Get Raspberry Pi and run program on there (my computer isn't always on at 9:00 AM everyday for CRON job to run)
4. Setup text message integration. I imagine this program texting you the number of crimes that have occurred from the previous day
5. Set up environment variables so I don't have to keep removing my password everytime I push

# How to sign up
* Go to *Insert Google form*

# Installation (for those who want to use program on their local machine)
* *insert*
