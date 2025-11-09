# Migrate-Outlook-1-Year-Mail-to-One-Drive-via-Powershell-Code
Migrate Outlook 1 Year Mail  to One Drive via Powershell Code

First Login to:
------------------
1. https://compliance.microsoft.com/
*  Data Life Cycle Management
******************************************
i. Exchange(Legacy)
* MRM Retention Tags
* + New Retention Tag
  + Archieve 1 Years Mail
  + Next
  + Tick Radio Button: Automatically to entire mailbox(default)
  + Next
  + Define Retention Setting
  + click radio button: When item reaches the following age (in days)
  + Insert in a blank box: 365
  + Click radio button: Move item to archieve
  + Next
  + Submit
***************************************
ii. Exchange(Legacy)
* MRM Retention policy
* + New Policy
* Archieve 1 Years Mail
* Add
* + Add tag
  + Next
  + Submit
***************************************

Second Login to:
--------------------

1. https://admin.exchange.microsoft.com/#/homepage
2. Go to exchange
3. Receipts
   *  Mailboxes
   *  Search user name: xitiz.basnet@xitiztechservices.com
   *  Select user: xitiz.basnet@xitiztechservices.com
   *  Go to the: Others
   *  Mailbox archieve(Manage Mailbox Archieve)
   *  Go to: Mailbox archeieve and see the Button (changed from off to ON)
   *  Get Back
   *  Go to the: Mailbox
   *  Look after the Retention Policy
           - Click: Manage mailbox policies
   *  See down:  + Retention Policy
                 + Default MRM Policy
                 + Mangage Mailbox Policies
   *  Go to: Retention Policy - and select Archieve 1 Years Mail
   *  Save
***************************************

Third Power Shell to:
--------------------
Administrator: Windows PowerShell (86)

*** START****

* PS C:\Users\Administrator> Get-Module -ListAvailable | Where-Object { $_.Name -eq "ExchangeOnlineManagement" }
* PS C:\Users\Administrator> Install-Module ExchangeOnlineManagement
* PS C:\Users\Administrator> Update-Module -Name ExchangeOnlineManagement
* PS C:\Users\Administrator> Import-Module ExchangeOnlineManagement
* PS C:\Users\Administrator> Connect-ExchangeOnline    
* PS C:\Users\Administrator> Enable-Mailbox xitiz.basnet@xitiztechservices.com -AutoExpandingArchive
* PS C:\Users\Administrator> Get-Mailbox xitiz.basnet@xitiztechservices.com | FL AutoExpandingArchiveEnabled
* PS C:\Users\Administrator> Enable-Mailbox xitiz.basnet@xitiztechservices.com -AutoExpandingArchive
* PS C:\Users\Administrator> Start-ManagedFolderAssistant -Identity xitiz.basnet@xitiztechservices.com
  
### (Note: If it does not start and face some error - Follow another step From begining)
* PS C:\Users\Administrator> Connect-ExchangeOnline -UserPrincipalName xitiz.basnet@xitiztechservices.com;   
* PS C:\Users\Administrator> Enable-Mailbox xitiz.basnet@xitiztechservices.com -AutoExpandingArchive
* PS C:\Users\Administrator> Get-Mailbox xitiz.basnet@xitiztechservices.com | FL AutoExpandingArchiveEnabled
* PS C:\Users\Administrator> Enable-Mailbox xitiz.basnet@xitiztechservices.com -AutoExpandingArchive
* PS C:\Users\Administrator> Start-ManagedFolderAssistant -Identity xitiz.basnet@xitiztechservices.com

*** END****

****************************************

Fourth Waiting to:
--------------------
**** Note: It may takes 24hour to 78 hours time to completely archieve the mail.
****************************************


--------------------
Thank You
--------------------






   




