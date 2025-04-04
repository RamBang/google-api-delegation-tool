# Gmail API Delegation Tool

This is an extremely lightweight Bash script that utilizes the Gmail API and GCP Console to delegate email inboxes to other users 
inside the same domain.

The preconditions are that you must delegate domain-wide authority to a service account, have the proper OAuth scopes added to the service account, and 
have a service account created.

Reference: https://developers.google.com/identity/protocols/oauth2/service-account#delegatingauthority

Google’s documentation is sparse and incomplete regarding the correct scopes needed for Gmail delegation.

Initially, the following scope was used:

https://www.googleapis.com/auth/gmail.settings.sharing

This scope allows creating and removing delegates, but fails when listing or retrieving them (via GET or LIST methods).

Reference: https://groups.google.com/g/google-apps-script-community/c/k9Q4mtdsEUw?pli=1

--------------------------

Therefore, adding the following scopes was mandatory: 

All scopes recommended: 

https://www.googleapis.com/auth/gmail.settings.sharing  
https://mail.google.com/  
https://www.googleapis.com/auth/gmail.modify  
https://www.googleapis.com/auth/gmail.readonly  
https://www.googleapis.com/auth/gmail.settings.basic  
https://www.googleapis.com/auth/gmail.metadata  

If the scopes or domain-wide delegation setup is incorrect, the JWT token will fail to generate and you will not be able to retrieve an access token.

https://support.google.com/a/answer/162106?hl=en&src=supportwidget0&authuser=0
