Short description of app_offline.htm

From Scot Gu's blog:
https://weblogs.asp.net/scottgu/App_5F00_Offline.htm-and-working-around-the-_2200_IE-Friendly-Errors_2200_-feature

The way app_offline.htm works is that you place this file in the root of the application.  
When ASP.NET sees it, it will shut-down the app-domain for the application (and not restart it for requests) 
and instead send back the contents of the app_offline.htm file in response to all new dynamic requests for 
the application.  When you are done updating the site, just delete the file and it will come back online.

One thing I pointed out in the talk that you want to keep an eye on is a feature of IE6 called "Show Friendly Http Errors".  
This can be configured in the Tools->Internet Options->Advanced tab within IE, and is on by default with IE6.  
When this is on, and a server returns a non HTTP-200 status code with less than 512 bytes of content, 
IE will not show the returned HTML and instead substitutes its own generic status code message

Other References:
https://docs.microsoft.com/en-us/aspnet/core/host-and-deploy/app-offline?view=aspnetcore-5.0

How to use:
Download the version you would like and remove the identifier after "app_offline.htm", and place
this file in your webapplications root folder.