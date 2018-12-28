# Smashing Onboarding

A collection of useful things and instructions. The onboarding includes:

- how to set up the local testing environment of smashingmagazine.com
- a cross-reference to various smashing URLs
- a list of who in the team does what


## A list of services you'll need access to:

- Notion, where we manage:
	- [Our projects](https://www.notion.so/smashing/d4344c8a01ff4b569acbccf5bd625526)
	- [Conferences](https://www.notion.so/smashing/6279875453324423b202b63f1e9a4041)
	- [Editorial](https://www.notion.so/smashing/7c3f14e9a2dc442d9448a8a090191f19)
- Dropbox, most likely including the `/Mailings/`, `/Membership/`, and `/Newsletter/` folders et al.
- Slack (https://smashingeditorial.slack.com/).
	- Make sure to join our [#standup](https://smashingeditorial.slack.com/messages/CD2FP7P97/) channel, too!
- Your own email address
- Mailchimp
- A Membership subscription
- Access to our [Github repositories](https://github.com/smashingmagazine)

## smashingmagazine.com local setup

It's highly recommended to set up your own local environment of smashingmagazine.com — it will safe you a lot of time when deploying updates.

To do so, clone [this repository](https://github.com/smashingmagazine/smashing-magazine) and run:

```
npm install
npm start
```

In case you have trouble running it, make sure to a) have *XCode* installed and b) then run the `npm cache clean` command and then try `npm start` again. 

Then visit `http://localhost:3000/` — BrowserSync will automatically reload the page when the CSS or content changes.

## Structure

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

## Basic Concepts

For the pattern library you'll probably mainly just want to work in the `src/css` folder with the SCSS files and use `site/layouts/index.html` and `site/layouts/partials` for the main HTML file and includes.

## Webinar updates

There's a number of things that need to be done on a regular basis around when webinar happen, and here's a checklist for it:

### Before the webinar:

- Check welcome mailings in `/Dropbox/Membership/mailings/00-welcome-emails/`... and upload them into Mailchimp ("ongoing campaigns") — they are pretty generic though, and only need updating if we have a major change
- Update order confirmation “You really do know how to make a cat happy! Thanks for registering for a webinar.” (`/Github/smashing-magazine/site/static/mails/order-confirmation.html`) — this still needs adding a webinar variable from Ilya, so at the moment, we can only mention the next upcoming webinar
- Tweet & FB it
- Send out reminder mailings & update Member Slack channel
- check setup with speaker

### After the webinar:
- update Smashing TV panel on the frontpage (smashingmagazine.com)
- Update `/smashing-tv/`
- Update Member dashboard: `/membership/#coming-up-next` and `/membership/#how-we-spent-the-money`