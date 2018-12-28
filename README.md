# Smashing Onboarding

A collection of useful things and instructions. The onboarding includes:

- how to set up the local testing environment of smashingmagazine.com
- a cross-reference to various smashing URLs
- a list of who in the team does what


## A list of services you'll need access to:

- A Membership subscription	
- Access to our [Github repositories](https://github.com/smashingmagazine)	
- Adobe Creative Cloud	
- Cloudinary, where we store our images	
- Dropbox, most likely including the `/Mailings/`, `/Membership/`, and `/Newsletter/` folders et al.	
- Mailchimp	
- Notion, where we manage:	
	- [Conferences](https://www.notion.so/smashing/6279875453324423b202b63f1e9a4041)
	- [Editorial](https://www.notion.so/smashing/7c3f14e9a2dc442d9448a8a090191f19)
	- [Our projects](https://www.notion.so/smashing/d4344c8a01ff4b569acbccf5bd625526)
- Our [CMS dashboard](https://www.smashingmagazine.com/admin/#/)
- Our [Shop dashboard](https://smashing-commerce.netlify.com/)
- Slack (https://smashingeditorial.slack.com/).	
	- Make sure to join our [#standup](https://smashingeditorial.slack.com/messages/CD2FP7P97/) channel, too!
- Your own email address	

That's a number of other services we use every now and then:

- Surveymonkey (for surveys)
- Zooom.us, for webinars, group calls, or calls with external people

Please use an app such as Lastpass, an extension available for Firefox, Chrome etc. to store your passwords safely. Get in touch with Markus who has all the credentials and will help you get access to these services

## smashingmagazine.com local setup

It's highly recommended to set up your own local environment of smashingmagazine.com — it will safe you a lot of time when deploying updates.

To do so, clone [this repository](https://github.com/smashingmagazine/smashing-magazine) and run:

```
npm install
npm start
```

In case you have trouble running it, make sure to a) have *XCode* installed and b) then run the `npm cache clean` command and then try `npm start` again. 

Then visit `http://localhost:3000/` — BrowserSync will automatically reload the page when the CSS or content changes.

### Structure

```
|--site                // Everything in here will be built with hugo
|  |--content          // articles, books, events, Smashing TV — all of it in one place.
|  |--data             // Includes author and speaker details
|  |--layouts          // This is where all page templates live
|  |  |--partials      // This is where includes live
|  |  |--index.html    // The index page
|  |--static           // Files in here ends up in the public folder
|--src                 // Contains all CSS and JS files
|  |--css              // SCSS files in the root of this folder will end up in /css/
|  |--js               // app.js will be compiled to /js/ app.js with babel
```

### Basic Concepts

For the pattern library you'll probably mainly just want to work in the `src/css` folder with the SCSS files and use `site/layouts/index.html` and `site/layouts/partials` for the main HTML file and includes.

## Webinar updates

There's a number of things that need to be done on a regular basis around when webinar happen, and here's a checklist for it:

### Before the webinar:

- Check welcome mailings in `/Dropbox/Membership/mailings/00-welcome-emails/`... and upload them into Mailchimp ("ongoing campaigns") — they are pretty generic though, and only need updating if we have a major change
- Update order confirmation “You really do know how to make a cat happy! Thanks for registering for a webinar.” (`/Github/smashing-magazine/site/static/mails/order-confirmation.html`) — this still needs adding a webinar variable from Ilya, so at the moment, we can only mention the next upcoming webinar
- Send out reminder mailings & update Member Slack channel
- check setup with speaker
- Tweet & FB it
	- To create a social sharing image, head over to `Dropbox/Membership/Webinars/` and use one of the .eps files to create a new sharing image (in Illustrator)
	- Keep the various social sharing image sizes in mind, here's an [overview](https://slide.ly/promo/image-resizer/)


### After the webinar:
- update Membership panel on the frontpage (smashingmagazine.com)
- Update `/smashing-tv/`
- Update Member dashboard: `/membership/#coming-up-next` and `/membership/#how-we-spent-the-money`

## Editorial Guidelines

a) Make sure to read the [article formatting guide](https://www.notion.so/smashing/Article-Formatting-Guide-765e814d88f44fbdb78da7ae5362de78), a guideline how to format code, images etc properly in Markdown

b) For our authors, we also have set up a [Style Guide](https://www.smashingmagazine.com/style-guide/) on the most common things that need to be kept in mind when writing an articles

c) To create a social sharing image for new articles, head over to `Dropbox/Editorial/social/` and use one of the .eps files to create a new sharing image. Keep the various social sharing image sizes in mind, here's an [overview](https://slide.ly/promo/image-resizer/)

## Who's doing what:

### Advertising, Books, Business planning

Cosima Mielke: produces our eBooks. Taking care of small Membership updates, too. Runs our wallpaper series.
Markus Seyffert: Taking care of the business side of Smashing. Also produces books, taking care of licenses, advertisers, sponsored articles.
Owen Gregory: proofreading, copyediting (print)

### Back office:

Inge Emmler: support requests, Membership status changes, accounting, invoices
Kristina Voigt: support emails
Jan Constantin: books fulfillment, book stand shipments, [web conf roundup](https://www.smashingmagazine.com/web-tech-front-end-ux-conferences/) update

### Design assets

Ricardo Gimenes, doing almost all of our illustrations.

If you need to update an existing artwork, e.g. social sharing image, you can also reach out to Markus

### Editorial

#### Core editors

Drew Mclellan: technical editor for CSS and PHP
Iris Ljesnjanin : author details, article updates, publishing, author
Rachel Andrew: **Editor in Chief**, article reviews, in control of the editorial
Rey Bango: technical editor for CSS and JavaScript
Yana Kirilenko: article and image uploads

#### Subject editors:
Alma Hoffmann: Contributing design editor
Andrew Lobo: proofreading
ChuiChui Tan: Contributing UX design editor
Heydon Pickering: Contributing accessibility editor
Marko Dugonjic: Contributing UX design editor
Michel Bozgounov: technical editor for (UX) Design tools, including Photoshop, Sketch, Illustrator, etc.

#### Core authors

Nick Babich: UX Design author, writes sponsored articles quite often
Suzanne Scacce: technical author, writes sponsored articles related to PHP, Wordpress but also UX quite often

### Events

Amanda Annandale: producer of SmashingConf New York and Toronto
Charis Rooda: website and mailings; tracking invited speakers
Marc Thiele: Chair of Board of Directors and conference photograph. Also our fallback MC.
Mariona A. Ciller: sponsorships and producer of SmashingConf San Francisco
Vitaly Friedman: inviting speakers, taking care of schedule and program, SmashingConf MC

### Memberships

Bruce Lawson: Senior Membership Manager
Scott Whitehead: Volunteers

### Technical Support

Ilya Pukhalski: technical support, when you run into issues related to CSS or JavaScript
Vitaly Friedman: major changes to our CSS
