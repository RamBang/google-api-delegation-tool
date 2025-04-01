# Gmail API Delegation Tool

This is a extremly lightweight bash script that utilizes Gmail API and GCP console to delegate email inbox's to other users 
inside the same domain. 

The preconditions are that you must delegate domain-wide authority to the service account, and proper scopes configured. 

Reference : 
https://developers.google.com/identity/protocols/oauth2/service-account#delegatingauthority

There is not much Google documentaiton on the correct scope/scopes to allow create,delete,get,list to work 

Reference: https://groups.google.com/g/google-apps-script-community/c/k9Q4mtdsEUw?pli=1

Scope : https://www.googleapis.com/auth/gmail.settings.sharing is what initially was tried. This works partly it allows the creation and deletion. However
it will not function properly with list and get. Therefore adding the following scopes was mandatory : 

All scopes recoemmended : 
https://www.googleapis.com/auth/gmail.settings.sharing
https://mail.google.com/
https://www.googleapis.com/auth/gmail.modify
https://www.googleapis.com/auth/gmail.readonly
https://www.googleapis.com/auth/gmail.settings.basic
https://www.googleapis.com/auth/gmail.metadata

If the scopes are not accurate or the domain-wide delegation config are not set the creation of the access token will not work. 



https://support.google.com/a/answer/162106?hl=en&src=supportwidget0&authuser=0