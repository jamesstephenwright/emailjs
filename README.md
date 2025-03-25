<!DOCTYPE html>\
<html lang="en">\
<head>\
    <meta charset="UTF-8">\
    <meta name="viewport" content="width=device-width, initial-scale=1.0">\
    <title>Anonymous Message Form</title>\
    <script src="https://cdn.emailjs.com/dist/email.min.js"></script>\
    <script>\
        (function() \{\
            emailjs.init("9tMbGXgcRBuPERdc7");  // Replace with your EmailJS User ID\
        \})();\
\
        function sendMessage(event) \{\
            event.preventDefault();\
            const message = document.getElementById("message").value;\
\
            emailjs.send("service_q98g7yk", "template_0ly2c8j", \{ message: message \})\
                .then(() => \{\
                    alert("Message sent successfully!");\
                    document.getElementById("message").value = "";\
                \})\
                .catch(error => \{\
                    alert("Failed to send message. Please try again.");\
                    console.error("Error:", error);\
                \});\
        \}\
    </script>\
</head>\
<body>\
    <form onsubmit="sendMessage(event)">\
        <textarea id="message" placeholder="Type your anonymous message here..." required></textarea>\
        <br>\
        <button type="submit">Send</button>\
    </form>\
</body>\
</html>
