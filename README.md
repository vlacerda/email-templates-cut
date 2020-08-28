This document describes the process used to generate and send emails and email templates.

### Summary
1. We create the email templates via a tool called [mjml](https://mjml.io/) for responsiveness in the emails.
2. The templates outputed by mjml are then loaded into an email delivery service called [sparkpost](sparkpost.com).
3. The internal backend system uses the sparkpost api to get the templates, inject the information into the template, generate the final HTML and send this HTML as an email.
4. The final HTML is then sent to the user.


### Files in this folder
1. Files that have the prefix "01-" are the mjml templates.
1. Files that have the prefix "02-" are the generated html templates after mjml.
1. The folder called 03-sent-emails has one example of a final email received by a user in gmail and saved as an HTML page.
1. "04-clipped-message-screenshot" is a screenshot showing that the delivered e-mails are being cut.
2. The folder "partial" is also part of the mjml templates. They have header, footer and other parts that are repeated in all emails.

### The problem
Emails are being sent via our platform and are cut short in gmail in seemingly random places.
We know that gmail has a cap in the size o the email it shows in the viewport but some of the emails
we analyse are well under the limit established by them.