spring-sendgrid
===============

A sample application for using Spring and SendGrid on Cloud Foundry.

### To test the application running on Cloud Foundry:

* `./gradlew assemble`
* `cf push`

When prompted to create a service for your app, select yes and choose SendGrid. This will provision an account on SendGrid and bind it to your app, which stores credentials for the account in the `VCAP_SERVICES` environment variable. This application will read those credentials and use them when it sends emails.

* browse to `http://spring-sendgrid.<cloud-foundry-domain>/`

You can verify what credentials the app is using by navigating to `http://spring-sendgrid.<cloud-foundry-domain>/creds`.

You can see what environment variables are available to the application by navigating to `http://spring-sendgrid.<cloud-foundry-domain>/env`.

You can override SMTP credentials by configuring them in `src/main/resources/application.properties`.

```
smtp.host=
smtp.user=
smtp.password=
```

### To run the application locally: 

* edit the file `src/main/resources/application.properties` and set your SendGrid host, user name, and password
* `./gradlew tomcatRun`
* browse to `http://localhost:8080/spring-sendgrid`

The first time `./gradlew` runs, it will take a while to download the build tool. Subsequent runs will be much faster. 
