## IMAP Trigger

Creates a connection to the e-mail server using the IMAP protocol and starts listening for push mail.

The tokens below are generated:

* \[CredentialData:Hostname\] - it contains the hostname of the IMAP Server;
* \[CredentialData:Username\] - it contains the email/username of the credentials used to contact the IMAP server;
* \[CredentialData:UseSSL\] - it mentions if SSL was used to connect to the IMAP Server;
* \[CredentialData:&lt;Key&gt;\] - it will be created with the custom data set in the Credential Section used for connection; 
* \[Mail:From\] - it contains the sender email; 
* \[Mail:FromName\] - it contains the sender's friendly name; 
* \[Mail:To\]  - it contains a list of emails with friendly name separated by comma; 
* \[Mail:Cc\] - it contains a list of emails with friendly name separated by comma;
* \[Mail:Bcc\] - it contains a list of emails with friendly name separated by comma;
* \[Mail:Subject\] - it contains the email subject; 
* \[Mail:DateSent\] - it contains the date when the email has been sent;
* \[Mail:Body\] - in contains the email body as HTML when it's set as HTML, otherwise it contains the text version;
* \[Mail:BodyText\] - it contains email body as a plain text;
* \[Mail:BodyHTML\] - it contains email body as a HTML;
* \[Mail:HasAttachments\] - it contains a boolean value which mention if the email has attachments;
* \[Mail:AttachmentsNameList\] -  it contains a list with all names of the attachments separated by comma.

**Credentials - **the mandatory  information for authorization.

* **Group** -  it contains the group name, configured in the Manage Credentials section, which can contain several emails \(entries\); 
* **Entry** -  in contains all entries available for a group, configured in the Manage Credentials section;

**WARNING: **For each credential in the group a thread will be created. We recommend you to limit this to 20 entries.

* **Edit Manage Credentials** opens a frame where the Groups and its entries can be configured. 
  * **Group Title** - the title used in the Credential option.
  * **Credential Entries** - set for a group:
    * **Entry Title** - determine a suggestive name for your entry; 
    * **Hostname** - the details of the incoming email \(IMAP\) server, for example imap.gmail.com:993 \(933 represents the required Port\); 
    * **Use SSL** - enable this option if your Email Server requires a SSL certificate;
    * **Username **- usually the full email address; 
    * **Password** - the email password;
    * **Custom Data** where can be appended a Data Key and a Data Value that can be used later in actions.
* **Start Date** - use this option to specify a starting date from which the trigger will scan e-mails. This will be updated with the last run time.
* **Make this go through all existing mail at the first run**. This will override the Start Date setting.
* **Compact body text **- it removes all empty lines and extra whitespace form the \[Mail:BodyText\] token.

* **Save Attachments** - enable this option for save the attached files.

* **Attachments save directory **- choose a directory where the files should be saved.

* **Filter E-mail by subject** - where a simple email subject can be appended. The below Use Regex option enabled will parse the complete email subject according to the set Regex expression.

* **Filter E-mail by recipient** - where a simple email address can be appended. The below Use Regex option enabled will parse the email recipients according to the set Regex expression.

* **Filter E-mail by sender** - where a simple email address can be appended. The below Use Regex option enabled will parse the email senders according to the set Regex expression.

* **Filter E-mail by Cc **-** **where a simple email address can be appended. The below Use Regex option enabled will parse the email cc recipients according to the set Regex expression.

* **Filter E-mail by Bcc** - where a simple email address can be appended. The below Use Regex option enabled will parse the email cc recipients according to the set Regex expression.

* **Filter E-mail by body **-** **where a simple plain text can be appended.The below Use Regex option enabled will parse the email body according to the set Regex expression.

* **Filter E-mail by attachments **- choose one of the following options: 

  * Has attachements

  * Doesn't have attachements

* **Custom Headers Filters - **If your emails have other headers than the ones above, add custom Header and Filter. 



