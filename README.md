# ringcentral-oauth-java
Demo application showing 3-legged OAuth 2.0 Flow for RingCentral platform using Java Web server (Jetty).

In general, the steps your app needs to take to use RingCentral APIs (including authorization) are as follows:

- Create an app, and obtain the app's credentials from your Developer Console account.
- Obtain an access token using either the authorization code flow.
- Use the access token in your HTTP Authorization header when calling a RingCentral API.
- Refresh your access token when necessary, as they can expire.

### Pre-requisites:

1. RingCentral Account (If you don't have one, you can create for free: https://www.ringcentral.com/signup.html)
4. RingCentral Developer Application. Get started creating a simple application by following this step by step guide: https://developers.ringcentral.com/guide/basics/create-app
5. Select OAuth for authentication and set `http://localhost:5000/oauth2callback` as the OAuth Redirect URI.


### Project Dependencies (build.gradle): It is advised to update the following dependencies to the latest versions.

1. JDK 11 or above
2. RingCentral Java SDK
2. Ecplise Jetty Server
3. Fastjson Library


### Setup:

1. Clone/Download this GitHub project
2. Open the project in your favorate Java IDE and navigate to WebApp.java.
3. Enter the values for the following two variables from your RingCentral Developer Application Settings - Sandbox Credentials. Optionally you can use Production Credentials as long as you change the `SERVER URL` field :

```java
  private static String CLIENT_ID = "RINGCENTRAL_APP_CLIENT_ID";
  private static String CLIENT_SECRET = "RINGCENTRAL_APP_CLIENT_SECRET";
```
5. Run `./gradlew build` to install the dependencies and compile and app
6. After successful execution and compilation, start the application server via gradle `./gradlew run `
7. Open your browser to **localhost:5000** and you will see **Login using RingCentral Account** link, click that and follow the wizard to login using your RingCentral Account.


8. Once you're logged in, you should be able to see options to call other RingCentral APIs such as to "Read Call Logs", "Extension Info" etc. This is done for the user who authorized the web app using OAuth 2.0 auth code flow.



