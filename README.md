# Snips-Einkaufsliste :memo:
With this app for [Snips.ai](https://snips.ai/) you can manage a shoppinglist with your voice.

##### Table of Contents  
[Features](#i-features)  
[Installation](#ii-installation)  
[Configuration](#iii-configuration)  
[Usage](#iv-usage)  
[Troubleshooting](#v-troubleshooting)  
[Contribution](#vi-contribution)  


## I. Features

- Ability to send the shoppinglist to an email address :postal_horn:

## II. Installation

:exclamation: The following instructions assume that [Snips](https://snips.gitbook.io/documentation/snips-basics) is
already configured and running on your device (e.g. a Raspberry Pi 3 from the 
[Snips Maker Kit](https://makers.snips.ai/kit/) with 
[Raspbian](https://www.raspberrypi.org/downloads/raspbian/) Stretch Lite). 
[SAM](https://snips.gitbook.io/getting-started/installation) should
also already be set up and connected to your device and your account.

1. In the German [app store](https://console.snips.ai/) add the
app `Einkaufsliste` (by domi; [this](https://console.snips.ai/store/de/skill_Va52B5v45GB)) to
your *German* assistant.

2. If you already have the same assistant on your platform, update it with:
      ```bash
      sam update-assistant
      ```
      
   Otherwise install the assistant on the platform with the following command to
   choose it (if you have multiple assistants in your Snips console):
      ```bash
      sam install assistant
      ```

3. With using SAM you will be asked to enter something
for the parameter "email_data". Below in the next section you 
can found the explanation of it.
    
## III. Configuration

You can configure the app so that it is able to send an email
containing the shoppinglist to an address.

:exclamation: Never enter credentials into a programm or website unless you know exactly what is happening to it.
In this case you can view the source code and see what is done
with it. The problem is that I could also simply insert code into the programm, which let it sent the login credentials
to me. But this should only be a warning, so that you know what is possible.
Be careful with your data!

The value of the parameter "email_data" is a string in form of a python dictionary.
Don't worry if you never heard of something like that.
Two curly brackets containing five items which are key-value pairs:
- "FROM": email address from which the shoppinglist will be sent
- "PASSWORD": password which belongs to the email address
- "HOST": SMTP host, ex.: "mail.gmx.net"
- "PORT": SMTP port, usually 587
- "TO": email address to which the shopping list will be sent

The email address used in "FROM" and "TO" can be the same.

*Examples:*

`{"FROM": "meinemail@gmx.net", "PASSWORD": "eb457fg9", "HOST":
"mail.gmx.net", "PORT": 587, "TO": "meinemail@gmx.net"}`

`{"FROM": "hello@gmx.com", "PASSWORD": "bo95345b3v", "HOST":
"mail.gmx.com", "PORT": 587, "TO": "hello@gmx.com"}`

Don't forget all the quotation marks and the curly brackets at the beginning and at the end!

With a Google email configuration you have to enable the option called like "allow external apps to send emails".

## IV. Usage

### 1. Example sentences

**Add item:**

- *Schreibe `Tomaten` auf meine Einkaufsliste.*
- *Kannst du bitte `Milch` auf meiner Einkaufsliste notieren?*

**Ask for item:**

- *Ist `Essig` schon auf der Einkaufsliste?*
- *Stehen `Himbeeren` auf meiner Einkaufsliste?*

**Get items:**

- *Was steht auf der Einkaufsliste?*
- *Lese meine Einkaufsliste vor.*

**Send list:**

- *Schicke meine Einkaufsliste per Email.*
- *Ich möchte die Einkaufsliste als Email auf mein Handy haben.*

**Delete item:**

- *Entferne `Kümmel` von der Einkaufsliste.*
- *Streiche `Apfelsaft` von der Einkaufsliste weg.*
- *Ich brauche keinen `Zimt` mehr.*

**Delete list:**

- *Lösche die Einkaufsliste.*
- *Entferne die gesamte Einkaufsliste.*


## V. Troubleshooting

- The time in the emails is wrong.

    Make sure that the time and date are correct on your device.
    
- I cannot see an email in my inbox, but Snips said it has been sent.
    
    Have a look in your spam folder.

## VI. Contribution

Please report errors and bugs (you can see them with `sam service log snips-skill-server` or on the Pi
with `sudo tail -f /var/log/syslog`) by opening
a [new issue](https://github.com/MrJohnZoidberg/Snips-Einkaufsliste/issues/new).
You can also write other ideas for this app. Thank you for your contribution.

Made with :blue_heart:
