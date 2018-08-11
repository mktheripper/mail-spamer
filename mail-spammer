# -*- coding: UTF-8 -*-
import smtplib
import datetime
import random
import getpass
import requests
import sys
import time
import argparse

class spammer():
    def __init__(self):
        self.banner()
        self.spam()

    def banner(self):
        print """   ____                             
  / __/__  ___ ___ _  __ _  ___ ____
 _\ \/ _ \/ _ `/  ' \/  ' \/ -_) __/
/___/ .__/\_,_/_/_/_/_/_/_/\__/_/   
   /_/  MarkDev SPAMMER V.1 
   """

    def spam(self):

        # Credentials
        username = raw_input("Enter Your Gmail: ")
        password = getpass.getpass()
        target = raw_input("Target Email: ")
        spams = input("No. Of Mails To Send:  ")
        server = smtplib.SMTP('smtp.gmail.com:587')
        server.starttls()
        try: server.login(username, password)
        except: print "[-] Authentication Error!" ; exit()

        print "[!] Engaging The Target"
        try:
            for i in xrange(spams):
                subj = 'Hello!'
                content = 'Hello World! by Mail'
                name = 'Mail Spammer'
                date = datetime.datetime.now().strftime( "%d/%m/%Y %H:%M" )
                msg = "From: %s\nTo: %s\nSubject: %s\nDate: %s\n\n%s" % (name, target, subj, date, content)

                server.sendmail(username, target, msg)
        except smtplib.SMTPException:
        		print "[-] An Error Occured During Process!"
        		print "[!] The Target Email Might Be Wrong!"
        		exit()
        server.quit()
        print "[+] Target Engaging Complete!"

try:
    spammer()
except KeyboardInterrupt:
    print "\n[-] Program Interrupted!"
    exit()
