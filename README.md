# Project
This project is about creating a webpage that downloads keylogger(malicious code) into user's system when user hits download button.The keylogger here sends the keystrokes user typed via gmail. The solution to this is to scan ports which are communicating with smtp server.

# Keylogger
The keylogger sends keystrokes of victim to the attacker through gmail.

# Keylogger Detector
Warns the user when a malicious process tries to send data from your machine.

## E-mail monitoring
Keyloggers work by logging all the keystores and storing the file locally for a fixed period of time, after which they send the log file to the hacker through a email.
Keylogger Detector monitors most used SMTP ports to detect the processes trying to communicate using 
### Popular SMTP servers monitored by Keylogger Detector
```smtp.gmail.com      SSL         465
smtp.gmail.com      StartTLS    587

smtp.live.com	    SSL         465
smtp.live.com       StartTLS    587

smtp.office365.com  StartTLS	587

smtp.mail.yahoo.com SSL         465

smtp.aol.com	    StartTLS	587

smtp.att.yahoo.com  SSL         465
...
```




