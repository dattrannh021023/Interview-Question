# • How to send an email without a mail client, just on the command line?

You can send an email from the command line using the `mail` command or other command-line email clients like `sendmail` or `ssmtp`. Here's an example using the `mail` command:

1. Open a terminal or command prompt.
2. Use the `mail` command with the recipient's email address to start composing an email. Replace `recipient@example.com` with the actual recipient's email address.

```bash
mail -s "Subject of the email" recipient@example.com

```

1. After running the above command, you'll be prompted to enter the email's content. Type your email message, and when you're done, press `Ctrl+D` to exit the text editor.
2. To send the email, press `Ctrl+D` again.

The email will be sent using the local mail server configured on your system. Make sure you have a working mail server set up, or the email may not be delivered.

Please note that this method is quite basic and might not work for sending emails through remote mail servers like Gmail or Yahoo. For more advanced use cases or when sending emails through specific mail providers, you may need to configure your mail client properly or use other command-line email clients like `ssmtp` or `sendmail`.