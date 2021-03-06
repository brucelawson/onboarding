# Smashing Onboarding

A collection of useful things and instructions. The onboarding includes:

- [How to set up the local testing environment](#smashingmagazinecom-local-setup) of smashingmagazine.com
- A list of services we use
- A checklist of [Webinar updates](#webinar-updates)
- An overview of active [product panels](#product-panel-updates)
- A list of [who in the team does what](#whos-doing-what)

# A list of services we use:

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
	- Make sure to join our [#standup](https://smashingeditorial.slack.com/messages/CD2FP7P97/) channel!
- Your own email address	

That's a number of other services we use every now and then:

- Surveymonkey (for surveys)
- Zoom.us, for webinars, group calls, or calls with external people

Please use an app such as Lastpass, an extension available for Firefox, Chrome etc. to store your passwords safely. Get in touch with Markus who has all the credentials and will help you get access to these services

# smashingmagazine.com local setup

It's highly recommended to set up your own local environment of smashingmagazine.com — it will safe you a lot of time when preparing updates.

To do so, clone [this repository](https://github.com/smashingmagazine/smashing-magazine) and run:

```
npm install
npm start
```

In case you have trouble running it, make sure to a) have *XCode* installed and b) then run the `npm cache clean` command and then try `npm start` again. 

Then visit `http://localhost:3000/` — BrowserSync will automatically reload the page when the CSS or content changes.


## **Structure**

```
|--site                // Everything in here will be built with hugo
|  |--content          // articles, books, events, Smashing TV — all of it in one place.
|  |--data             // Includes author and speaker details
|  |--layouts          // This is where all page templates live
|  |  |--partials      // This is where includes live
|  |  |--index.html    // The index page
|  |--production-articles // where all of our articles live
|  |--static           // Files in here ends up in the public folder
|--src                 // Contains all CSS and JS files
|  |--css              // SCSS files in the root of this folder will end up in /css/
|  |--js               // app.js will be compiled to /js/ app.js with babel
```


## **Basic Concepts**

For the pattern library you'll mainly work in the `src/css` folder with the SCSS files and use `site/layouts/` to update various partials in our dashboard, the content, and our [product panels](#product-panel-updates).

# Membership & Webinar updates

There's a number of things that need to be done on a regular basis around when webinar happen, and here's a checklist for it:


## **Before the webinar:**

- Check welcome mailings in `/Dropbox/Membership/mailings/00-welcome-emails/`... and upload them into Mailchimp ("ongoing campaigns") — they are pretty generic though, and only need updating if we have a major change
- Update order confirmation “You really do know how to make a cat happy! Thanks for registering for a webinar.” `/Github/smashing-magazine/site/static/mails/order-confirmation.html` — this still needs adding a webinar variable from Ilya, so at the moment, we can only mention the next upcoming webinar
- Send out reminder mailings & update Member Slack channel
- check setup with speaker
- Tweet & FB it
	- To create a social sharing image, head over to `Dropbox/Membership/Webinars/` and use one of the .eps files to create a new sharing image (in Illustrator)
	- Keep the various social sharing image sizes in mind, here's an [overview](https://slide.ly/promo/image-resizer/)


## **After the webinar:**
- update the Membership popup on smashingmagazine.com (`/site/layouts/partials/membership-popup.html`)
- Update `/smashing-tv/` (`/site/content/smashing-tv/`)
- Update the Member dashboard: 
	- Please update `/membership/#coming-up-next` (`/site/layouts/partials/coming-up-paid.html`) and (`/site/layouts/partials/coming-up.html`)
	- Please update `/membership/#how-we-spent-the-money` (`/site/layouts/partials/spendings.html`)
	- Add the link to the webinar recordings (`/site/layouts/partials/webinars.html`)

# Product Panel updates

A list of _active_ product panels that are included in all of our articles (and for non-members), which you'll find in `/site/layouts/shortcodes/`:


## **Product Panels (articles)**

- The main product panel `{{% feature-panel %}}`, currently featuring Smashing Book 6
- The Case Study panel `{{% feature-panel--case-study %}}`, currently featuring Form Design Patterns
- The conference panel `{{% feature-panel--conference %}}`, promoting our conferences (currently SmashingConf San Francisco)

- `{{% feature-panel %}}`, currently featuring Smashing Book 6
- `{{% feature-panel--conference %}}`: promoting our conferences (currently SmashingConf San Francisco)
- `{{% feature-panel--case-study %}}`: currently featuring Form Design Patterns
- `{{% feature-panel--workflow %}}`: Smashing TV
- `{{% feature-panel--perf %}}`: articles, books, memberships
- `{{% feature-panel--ux %}}`: Design Systems


## **Frontpage Panel**

Last but not least, the *Membership Adblock popup*, which appears only for not logged-in users who are using an adblocker:

You'll find it in `/site/layouts/partials/membership-popup.html`. It needs to be regularly updated, especially after every webinar.


## **Unused Panels**

There is also a number of currently _unused_ but available panel templates, including:

- `{{% feature-panel--design-systems %}}` (about the Design Systems book)
- `{{% feature-panel-toronto %}}` (about SmashingConf Toronto)
- `{{% feature-panel--coming-up %}}` A list of upcoming webinars


## **Discounts & Goodies**

Please also check:

- the discounts section once a month (`/site/layouts/partials/coupons.html`) if the coupon codes still work
- and if the goodies section (`/site/layouts/partials/goodies.html`) can be updated

# Editorial Guidelines

a) Make sure to read the [article formatting guide](https://www.notion.so/smashing/Article-Formatting-Guide-765e814d88f44fbdb78da7ae5362de78), a guideline how to format code, images etc properly in Markdown

b) For our authors, we also have set up a [Style Guide](https://www.smashingmagazine.com/style-guide/) on the most common things that need to be kept in mind when writing an articles

c) To create a social sharing image for new articles, head over to `Dropbox/Editorial/social/` and use one of the .eps files to create a new sharing image. Keep the various social sharing image sizes in mind, here's an [overview](https://slide.ly/promo/image-resizer/)

# Who's doing what:


## **Advertising, Books, Business planning**

**Cosima Mielke**: produces our eBooks. Taking care of small Membership updates, too. Runs our wallpaper series.

**Markus Seyfferth**: Taking care of the business side of Smashing. Also produces books, taking care of licenses, advertisers, sponsored articles.



## **Back office:**

**Inge Emmler**: support requests, Membership status changes, accounting, invoices

**Kristina Vogt**: support emails

**Jan Constantin**: books fulfillment, book stand shipments, [web conf roundup](https://www.smashingmagazine.com/web-tech-front-end-ux-conferences/) update


## **Design assets**

Ricardo Gimenes, doing almost all of our illustrations.

If you need to update an existing artwork, e.g. social sharing image, you can also reach out to Markus


## **Editorial**


## **Core editors**

**Cosima Mielke**: Runs our Smashing Wallpaper series

**Drew Mclellan**: technical editor for CSS and PHP

**Iris Ljesnjanin**: author details, article updates, publishing, author

**Rachel Andrew**: _Editor in Chief_, article reviews, in control of the editorial

**Rey Bango**: technical editor for CSS and JavaScript

**Yana Kirilenko**: article and image uploads


### Subject editors

**Alma Hoffmann**: Contributing design editor

**Andrew Lobo**: proofreading

**ChuiChui Tan**: Contributing UX design editor

**Heydon Pickering**: Contributing accessibility editor

**Marko Dugonjic**: Contributing UX design editor

**Michel Bozgounov**: technical editor for (UX) Design tools, including Photoshop, Sketch, Illustrator, etc.

**Owen Gregory**: proofreading, book editing, copyediting (print)


## **Core authors**

**Nick Babich**: UX Design author, writes sponsored articles quite often

**Suzanne Scacce**: technical author, writes sponsored articles related to PHP, Wordpress but also UX quite often



## **Events & Event Sponsorships**

**Amanda Annandale**: producer of SmashingConf New York and Toronto

**Charis Rooda**: website and mailings; tracking invited speakers

**Marc Thiele**: Chair of Board of Directors and conference photograph. Also our fallback MC.

**Mariona A. Ciller**: sponsorships and producer of SmashingConf San Francisco

**Vitaly Friedman**: inviting speakers, taking care of schedule and program, SmashingConf MC



## **Memberships**

**Bruce Lawson**: Senior Membership Manager

**Scott Whitehead**: _Smashing_ Volunteer, taking care of various Membership updates.

**Cosima Mielke**: Taking care of small Membership updates, including the dashboard, mailings, or the Member counter. if Scott isn't available.



## **Technical Support**

**Ilya Pukhalski**: technical support, when you run into issues related to CSS or JavaScript

**Vitaly Friedman**: major changes to our CSS



## **C-Level People**

**Vitaly Friedman** has co-founded the company and ownes the majority of Smashing, which means he always has the last word. He also is a member of our  board of directors.

**Marc Thiele** is the Chair of our board of directors, and gives his advice on various things, but especially as for our conferences

**Paul Boag** is a member of our board of directors, and gives more strategic advice every now and then

**Inge Emmler** (CEO) does the accounting and invoices stuff, and all the nasty paperwork

**Markus Seyfferth** (CEO) runs the business side of Smashing and also takes care of financial plannings, forecasts, and advertising / sponsoring partners