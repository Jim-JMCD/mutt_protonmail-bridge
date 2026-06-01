# mutt_protonmail-bridge

## Guide for installing, configuring and using the Mutt mail client with Proton Mail Bridge on Linux Server and Linux Desktop.

#### Full Guide : [Mutt_ProtonMail-Bridge_Guide](https://github.com/Jim-JMCD/mutt_protonmail-bridge/blob/main/Mutt_Proton_Mail-Bridge_Guide.pdf) _See Mutt_Proton_Mail_Bridge_Guide.pdf in repo file list_
#
System, security and application administrators use command line mail tools like sendmail, postfix, mailx and mutt to mail out reports alerts and other material to people that presumably care. This guide describes how setup up command line mail service using Proton Mail Bridge combined with the Mutt mail client.

On Linux Desktop, Thunderbird is supported by Proton and may be a better option for sending emails from the command line. 

If the requirement is only to send mail from a Linux computer, using postfix and Proton Mail as a send only SMTP server may be an alternative option. _To use Proton Mail as a SMTP server requires a functioning custom domain in the mail account._    

### Scope limitations

* This guide only covers the basics of how to configure and use mutt. The goal is to have a workable solution that can be enhanced and tailored further for your individual requirements.
* Setting up protonmail-bridge as a daemon-like process in this guide for Linux Server is limited to the basics, full systemd implementation is out of scope.  Deamonizng on Linux Desktop not covered in this guide
* These installation and configuration notes use the defaults, further modifications to permissions and security features may be required for a more secure environment.
* Software installation is out of scope. Software package management varies between Linux flavours

At time of writing:
* Proton Mail Bridge is not supported ARM devices other than M-series Macs.
* The only Proton supported mail client for the Linux Proton Mail Bridge is Thunderbird.  

### Summary of steps

* Create user account for this installation and usage of mutt and protonmail-bridge. [Optional]
* All the following to done in the designated user account. All software installations to be done as root.
1. Install protonmail-bridge.
1. Install the password manager, pass.
1. Initialise the password manager (pass) with a gpg password.
1. Start protonmail-bridge interactively to initialise and sync protonmail-bridge. The protonmail-bridge is configured only for the designated Linux user account and creates a database within the home directory of that user. The sync process may take hours with large accounts that contain 10,000+ emails resulting in taking up GiBs of disk space within the users home directory. 
1.	Install w3m.  Used by mutt to convert html text into easy human readable text.
1.	Create the w3m configuration file in the user’s home directory.
1.	Create the mutt default configuration file in the user’s home directory.
1.	Install mutt
1.	Start protonmail-bridge in the background, alternatively start it another window using the designated
