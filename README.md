# External Login (Login with Facebook and Google)

# By Using ASP.net Core WebAPI and ASP Identity
<br>

### Introduction
The two most important parts of the projects:

* **API\ExternalLoginController:** i added this API Controller to implement logging with FB and Google functionality
* **Areas\Identity\Pages\Account:** i did extract Identity internal login pages to be used as reference
<br>

### To Use

* Create FB and Google Reeferences, use following linkgs from 
    * facebook: [https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Facebook](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Facebook)
    * google: [https://developers.google.com/identity/sign-in/web/devconsole-project](https://developers.google.com/identity/sign-in/web/devconsole-project)
* use following links as callback links in facebook and google:
    * for facebook: [https://localhost:44392/signin-facebook](https://localhost:44392/signin-facebook)
    * for google: [https://localhost:44392/signin-google](https://localhost:44392/signin-google)
* right click on the project file select (Manage user Secrets), add the following

```
{
  "Authentication:Facebook:AppId": "",
  "Authentication:Facebook:AppSecret": "",
  "Authentication:Google:ClientId": "",
  "Authentication:Google:ClientSecret": ""
}
```

* don't forget to update-database
* Then call ([https://localhost:44392/api/ExternalLogin/FacebookLogin](https://localhost:44392/api/ExternalLogin/FacebookLogin)) or ([https://localhost:44392/api/ExternalLogin/GoogleLogin](https://localhost:44392/api/ExternalLogin/GoogleLogin)). 
* after authontication the user, it will call back the funciton **(CallBack)**. and extract all external claims and put them in the variable (info). if the user did exist it will log him in, else it will create him.
* you can also use the usual mvc interface to login with facebook and google by going to login page.
<br><br>

### References:
* [https://docs.microsoft.com/en-us/aspnet/core/security/authentication/social/?view=aspnetcore-3.1&tabs=visual-studio](https://docs.microsoft.com/en-us/aspnet/core/security/authentication/social/?view=aspnetcore-3.1&tabs=visual-studio)
* [https://www.blinkingcaret.com/2018/10/10/sign-in-with-an-external-login-provider-in-an-angular-application-served-by-asp-net-core/](https://www.blinkingcaret.com/2018/10/10/sign-in-with-an-external-login-provider-in-an-angular-application-served-by-asp-net-core/)
* [https://stackoverflow.com/questions/55296041/updating-default-front-end-design-of-identity-login-page-in-net-core](https://stackoverflow.com/questions/55296041/updating-default-front-end-design-of-identity-login-page-in-net-core)
* [http://docs.identityserver.io/en/latest/topics/signin\_external\_providers.html](http://docs.identityserver.io/en/latest/topics/signin_external_providers.html)
* [https://stackoverflow.com/questions/48120508/net-core-external-authentication-without-asp-net-identity](https://stackoverflow.com/questions/48120508/net-core-external-authentication-without-asp-net-identity)

<br>
<br>
