# NodeMailer
boiler plate to send email via nodejs

const nodemailer = require("nodemailer")
const email = "yourMAil@gmail.com";
const pass = "your app password";

const transporter = nodemailer.createTransport({
    service: "gmail",
    auth: {
        user: email,
        pass:pass
    }
})

const message = {
    from: email,
    to: " whom you want to send",
    subject: "Sending email ",
    text: "hello from nodejs",
    html: {path:"send.html"} or html:"<h1>Hii</h1>"
}

transporter.sendMail(message, function (err, info) {
    if (err) {
        console.log(err)
    } else {
        console.log("Email sent:"+info.response)
    }
})
