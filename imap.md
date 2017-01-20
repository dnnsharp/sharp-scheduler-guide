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
* \[Mail:Subject\] - it contains the email's subject; 
* \[Mail:DateSent\] - it contains the date when the email has been sent;
* \[Mail:Body\] - in contains the email's body as HTML when it's set as HTML, otherwise it contains the text version;
* \[Mail:BodyText\] - it contains email's body as a plain text;
* \[Mail:BodyHTML\] - it contains email's body as a HTML;
* \[Mail:HasAttachments\] - it contains a boolean value which mention if the email has attachments;
* \[Mail:AttachmentsNameList\] -  it contains a list with all names of the attachments separated by comma.

**Credentials - **the mandatory  information for authorization. 

* **Group** -  it contains the group name, configured in the Manage Credentials section; 
* **Entry** -  in contains all entries available for a group, configured in the Manage Credentials section;

**WARNING: **For each credential in the group a thread will be created. We recommend you to limit this to 20 entries.

* **Edit Manage Credentials** opens a frame where the Groups and its entries can be configure. 
  * **Group Title** - the title used in the Credential option. 
  * **Credential Entries** - set for a group:
    * **Entry Title** - determine a suggestive name for your entry; 
    * **Hostname** - the details of the incoming email \(IMAP\) server, for example imap.gmail.com:993 \(933 represents the required Port\); 
    * **Use SSL** - enable this option if your Email Server requires a SSL certificate;
    * **Username **- usually the full email address; 
    * **Password** - the email password;
    * **Custom Data** where can be appended a Data Key and a Data Value that can be used later in actions.



