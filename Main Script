import os
import tweepy
import random
import datetime
import requests
import smtplib
from email.mime.text import MIMEText

email = "email for the account"
password = "password"

to_email = "check"

smtp_server = "smtp.gmail.com"
smtp_port = 587

consumer_key = "keys"
consumer_secret = "keys"

access_token = "keys
access_token_secret = "keys"

auth = tweepy.OAuth1UserHandler(consumer_key, consumer_secret, access_token, access_token_secret)
api = tweepy.API(auth)

folder_path = os.path.abspath(os.path.join("C:\\Users\\DDI", "twitter"))

photo_files = os.listdir(folder_path)

try:
    requests.get("http://www.google.com")

    random_photo = random.choice(photo_files)
    _, file_extension = os.path.splitext(random_photo)
    photo_path = os.path.join(folder_path, random_photo)
    media = api.media_upload(photo_path)
    api.update_status(status="Today's Artificially Generated Photo, Selected on " + str(datetime.date.today()) + " #AI", media_ids=[media.media_id])
except Exception as e:
    subject = "Twitter bot error"
    message = "An error occurred while running the twitter bot: " + str(e)
    msg = MIMEText(message)
    msg['Subject'] = subject
    msg['To'] = to_email
    s = smtplib.SMTP(smtp_server, smtp_port)
    s.starttls()
    s.login(email, password)
    s.send_message(msg)
    s.quit()
finally:
    print("Done")
