# c8oprj_lib_openid_admin
This library enables Convertigo administrators to connect using OpenID to access the admin console.

This is a template project you can cutomize for your needs. Customization points are :

* On MobileApplication->Application->Pages->Page->events->onDidEnter->OAuthLogin object :
  * Set the __Authorization endpoint__ to your OpenID IDP authorization endpoint url
  * Set the __Cliend ID__ to your IDP ClientID 

* Customize the Sequences->PeformAdminLogin to decide if the id_token received represents a valid Convertigo user. for this, you will have to call your OpenID IDP with this tokenID and get information about the user. This is specific to each IDP.
* Compare the user authenticated to the list of __validAdminUserList__ and reject if the authenticated user is not on the list.

Deploy this project to a Convertigo server and use the 

```
http://[yourserver]:[port]/convertigo/projects/lib_OpenIDAdmin/DisplayObjects/mobile/index.html#login
```
 
url to access the Convertigo admin console. A Window will popup (You might have to Authorize popups on this site...) asking for your IDP credentials. Fill them in, validate.

If your OpenID cerdentials are ok, and if your user is in the __validAdminUserList__ you will be redirected to the Convertigo Admin console with admin privileges.


