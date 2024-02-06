+++
date = "2021-02-28"
author = "Bob Hyman"
draft = false
title = "Changing password managers, LastPass to Bitwarden"
tags = [ "Personal IT", "Software" ]
images = ["markus-winkler-OjSG0E_qcbo-unsplash.jpg"]
+++
Converting from LastPass password manager to Bitwarden, or getting started with Bitwarden, there being no time like the present.
<!--more-->

LastPass has had a great run as the best-of-breed password manager for the masses.  But now, their corporate masters, LogMeIn Inc., have decided to stop giving it away and to see if they can extract a rent for their useful service.  I don't begrudge their desire to be reimbursed for their work, we non-programmers won't have good choices if the craftsmen can't make a living at it.  But LogMeIn adds a whole 'nother layer of management and marketing on top of the core product and thinks this should command a price premium.  I don't agree, so when they pull this move, I move on. 

Currently, the internet is full of alternatives to consider or ways to rationalize paying the rent.  Myself, I've decided to switch to Bitwarden and am recommending you do likewise.  I think it's a comprehensive solution for most users with ordinary needs.

## Procedure

Here's how to migrate from LastPass to Bitwarden with specifics for Chrome browser on a PC and an app on Android phones or tablets.  If you are invested in the Apple ecosystem, you'll have to look elsewhere for specifics though you may be able to translate these procedures through the Reality Distortion Field.

1. Log into LastPass web site one last time, export your whole secure store to a CSV file.  (You can't do this in the LastPass app.)

   a. On your desktop (Windows, Apple, Linux...), log into https://lastpass.com

   b. From the website main page, left column, choose "Advanced Options", "Export" (and thanks to LastPass for making this easy!)

   c. this will produce a file containing all your pretties in `~/Downloads/last_pass.csv`

2. Log into https://bitwarden.com,  create a new account and import the CSV data.  You'll have to choose a master password, just like LastPass.  Resist the temptation to use the same one!  Virtue, like Charity, starts at home!  Like LastPass, there is no "forgot password" capability to reset your master password by email or notification.  If you forget it, it's gone, man.  I have written down my master password and saved it where I keep the key for my safe deposit box.

   a. In the top menu, choose "Tools", "Import Data"

   b. In the Import menu, select format "LastPass (csv)", and the above exported CSV file.

   c. Expect to see all your saved info populate in the Bitwarden vault.

3. *Delete* the CSV file (Virtue begins where?)

4. While you're still on the desktop, install the Bitwarden extension for Google Chrome (the process is similar for other browsers):

   a. In the Chrome settings menu (3 vertical dots), "More Tools", "Extensions", *disable* or *remove* the LastPass extension.  If you ever need to get back into LastPass, you can visit to the website.

   b. Browse to https://chrome.google.com (Google Chrome app store) and search for "Bitwarden" extension and install it.

   c. Open the extension (look for the extensions icon, a jigsaw puzzle piece, in the upper right of the browser).

   d. In the extension window, click "Settings" (bottom right)

   e. In settings, set "Vault timeout action" to "Lock" and enable "Unlock with PIN" and/or "Unlock with biometrics"  (so you don't have to keep typing your master password; this should *never* become habitual!).  
   
5. And finally, suppress Google Chrome's own password manager.  
Like me, you may have allowed Google to fill some passwords in the past and are not quite ready to have it forget them.  But you do want to be sure Bitwarden is up to date.  So, turn off browser password management but don't delete whatever synched passwords it has.  Later, when you're comfortable with Bitwarden, you can delete this redundant copy of secrets (even though they'll hopefully be obsolete by then, anyway.)

	a. At the 3 dot menu, "Settings", Autofill, Passwords
	
	b. In the Passwords page, *disable* "Auto Sign-in" and "Offer to save passwords".  These settings will be synced to all devices on which you signed into Chrome.

On your phones or tablets:
1. Remove the LastPass app.  Since you've already initialized your Bitwarden vault online, you don't need to export / import on each device.
2. Install the Bitwarden app.  Double check you're getting the authentic app from "Bitwarden, Inc", its rise in popularity will no doubt attract cybercriminal attention.
3. Open the app, log in with same user name and master password as you established above.  Verify you see the expected list of saved passwords here on your device, too.
4. Still in the app, adjust settings.  It's rather a longer list, but this is what makes it convenient where you'll be using it most frequently:
	a. "Autofill Services": on the next page, *enable* "Autofill Services" and "Use Accessibility", but you (probably) don't need "Use Draw-over".  Android will ask for confirmation with its own settings dialog for each of these.
	b. "Unlock with PIN code", *enabled*.  It will prompt with additional confusing question, "Do you want to require unlocking with master password when the application is restarted?".  The correct answer is "No".  
	This does mean if someone unlocks your phone, they can access all your passwords if they can guess this PIN.  But the alternative is worse, that you become habituated to typing your master password indiscriminately and will someday type it into a spoofed login dialog.

Try this at home:
Having made all these changes, verify that everything is working.  

1. Open the browser and visit a site where you have an account. 
   The first use after a reboot or long idle time, expect to have to click in the username field before Bitwarden does anything. And when you do, you'll see a humble prompt clearly labeled with Bitwarden that says "vault is locked".  Tap the link and enter your PIN to proceed.  Subsequent visits to the same or other known websites will offer a list of usernames for that site (even if there is only one).  But either way, you'll have to tap on the option to complete the login.  I find this more unobtrusive and straightforward than LastPass, which tried to hide the whole login negotiation, but failed more often than not.  Your mileage may vary, and there are options you can tweak to automate more. 
2. Open the Bitwarden app or website, log in with your PIN or master password, and review the contents of the vault.  If you're anything like me, you'll find multiple variations on the web address are stored as duplicate entries with duplicate username/password info.  You can clean these up manually, or, if (again like me) you have many of these, you can automate the process a bit by exporting the vault to CSV, cleaning it up with a text editor (Excel is not advised, it messes with quotes and things that might be dates), the importing it again.

## Rationale

My firm recommendation is that all we internet civilians use some kind of password manager and use different, unique (e.g, generated) passwords for each and every web service.

I think Bitwarden is the best option for most internet civilians, Google Chrome synced passwords next after that, but would like to hear your opinions and the tradeoffs that guide you.  

Here's my rationale for Bitwarden:

Bitwarden has been around for many years, though drowned out by Lastpass' relentless marketing.  It's a technically sound, multi-platform solution (runs on the holy trinity: PCs, Android, Apple) with an respectable open source implementation.  They use a fairly slick and unobtrusive design to autofill your password info into websites and apps (cleaner than LastPass, sez me). There's a company behind it (not every open source project can have a van Rossum or Torvalds driving it, corporate organization is the next best thing) and the  they're committed to forever free personal use and offer support.  Like LastPass, they insist on using their own cloud for storing your sensitive info, so there's additional overhead costs to be recovered and the subscription model is baked in.  If they allowed you to store your info in your own cloud storage (Box, *Drive, what have you), they could see their way to a Patreon or Go Fund Me pay-what-you-can model.  

