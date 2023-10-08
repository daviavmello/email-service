# email-service
The `email-service` is a Spring-based RESTful service for sending email messages. It facilitates the integration of email-sending functionality into a Spring application by providing an HTTP endpoint (/email/send) that allows clients to send emails programmatically.
## Technologies
 
- [Spring Boot](https://spring.io/projects/spring-boot)
- [JavaMailSender](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/mail/javamail/JavaMailSender.html)

## How to Run

### Locally
- Clone the git repository
- Build the project:

```
./mvnw clean package
```
- Execute:
```
java -jar email-service/target/email-service-0.0.1-SNAPSHOT.jar
```

### Sending an Email
To send an email using the EmailController, make a POST request to the `/email/send` endpoint with a JSON payload representing the email message. The request should contain the following properties:

- to: The recipient's email address.
- subject: The subject of the email.
- message: The email message content.

Example Request:
```
http
Copy code
POST /email/send
Content-Type: application/json

{
    "to": "recipient@example.com",
    "subject": "Hello, World!",
    "message": "This is a test email message."
}
```

### Response
The EmailController responds to successful email sending with a JSON response containing the following information:

- HTTP Status Code: 200 OK
- Response Body: "Success"
  
In case of errors during the email-sending process, an error message is sent back as a response:
```
"An error occurred: " + e.getMessage();
```
