## Send email using java (java mail api)
A platform & protocol independent framework to build mail & messaging applications.
```xml
<dependency>
    <groupId>com.sun.mail</groupId>
    <artifactId>javax.mail</artifactId>
    <version>1.6.2</version>
</dependency>
```
we need two jar mail.jar, activation.jar to use this service

## Important class & interface 

* ***java.util.properties:-*** is used to saved information in key value pair
* ***javax.mail.message:-*** model of email message.to send a email, subclass of Message is intanted.
* ***javax.mail.MessagingException:-*** base class for exception thrown by the Messaging class 
* ***javax.mail.PasswordAuthenticator:-*** this class is simply a repository for a username & password.

* ***javax.mail.Session:-*** represents a mail session
* ***javax.mail.Transport:-*** Abstract class contains static send(), use to send message.
* ***javax.mail.internet.InternetAddress:-*** represents an internet email address syntax of RFC822
* ***javax.mail.MimeMessage:-*** represents MIME style message.it implements the Message abstract class & the MimePart Interface

### steps to send mail
1. get the session
2. compose the mail
3. send the mail
