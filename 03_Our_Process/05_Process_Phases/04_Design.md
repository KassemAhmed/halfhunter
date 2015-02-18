## Guidelines for the Design Process

### Photoshop basics

Make a new PSD file for every page. 
Do not create multiple pages within one document.
Save PNG files of everything for quick referencing and Basecamp posts.
Save often! There's nothing worse than accidentally losing a day's work.

### Naming conventions

Keep it relevant. If you create a blue button, make sure it’s named ‘bluebutton’ or something similar. This helps developers find elements more quickly.

### Interaction States (Checklist)

- Hover, active ('clicked'), and disabled states for buttons
- Hover and active states for nav elements
- Hover states for links if applicable(also active and visited)
- Any drop-down menus or elements that appear on click/hover
- Any tooltips 
- Focus, error, and disabled styles for forms
- Any other states that are not immediately viewable on page load

### Designing responsive sites

- Create alternatives to modal windows.
- Mockup how the navigation should be arranged.
- Mockup content choreography as much as possible.
- Run ideas for interactions past developers before starting design, to make sure that the idea can be coded.

### Designing for email

There are a lot more restrictions when it comes to developing email newsletters than regular websites, and there are a lot of things that unfortunately just can't be done reliably, so are probably best avoided. A few pointers:

- Try not to use images to convey important information, since they won't be shown by default in many clients.
- No fancy fonts please! No javascript = no typekit. It sucks, but you can really only use web-safe fonts. Even for headings. This is a decent reference. Remember: any element on the page that is not a web-safe font will have to be coded as an image, and will therefore not be displayed in -some email clients by default.
- Remember that background images will not show up in all clients. You can add them in as a nice touch for those clients that do support them, but make sure it would look okay with a solid colour background.
- Try not to get too fancy with layout: remember, we have to code these up using tables :p
- Keep it simple!

### Designing forms

These guidelines are in place to make the coder’s life easier. Forms are difficult to style, cause browser discrepancy problems, and are an all-around pain in the ass.

Thanks to modern tools, we’ve got a lot more control over forms. But there are still problematic areas. Some things to avoid:

- Number inputs don't style well.
- Don’t put icons in select menus!
- Be careful using placeholder text only on text inputs. If the form will be revisited later with values pre-populated, context might be lost.

### Miscellaneous Items (checklist)

Don't forget!

- 404 pages
- Email templates
- Blank dashboard placeholders
- Instructions/tours for first-time users

## Preparing Your Design Elements

*Before you begin the design phase* (prior to project, during kickoff, or during UX phase), make sure you decide on and get the client to approve all of the following design elements. Doing this *before you include options in your design mockups* prevents both extra work for your developer, and unforeseen costs for your clients.

**Iterative Workflow:** Each of these items should go through the [iterative workflow](/Our_Process/Iterative_Workflow/) process in Trello, like any other task.

**Templates:** We have cards in the project template board in Trello called "Web Fonts Discussion," "Stock Photos/Videos Discussion," and "Additional Design Elements Discussion (Audio, icon sets, etc.)" to remind you to have these discussions with your clients.

### Picking Web Fonts

When picking web fonts, our development team recommends that you stick to the following options:

- [Google Fonts](https://www.google.com/fonts)
- [FontSquirrel](http://www.fontsquirrel.com/)
  - Double check the license before you use a FontSquirrel font
  - Also it's possible to run an openly-licensed font through FontSquirrel for web embedding.
- [TypeKit](https://typekit.com/)
- [Cloud.Typography](http://www.typography.com/cloud/welcome/)
- Any other site that sells/licenses webfonts

Note that web-fonts often use traffic-dependent pricing models. TypeKit, for instance, can get very expensive for large businesses whose websites are visited frequently. In a case like that, a free Google Font or a commercial font with a one-time fee would be a better choice.

*Before* we can use a font in a design, the client must be notified and approve the cost. Fonts must be presented, and the client must purchase the font or sign up for a web font account. **Ideally, this is done in the kickoff or UX phase.** It *must* be done prior to the design phase.

### Stock Photos/Videos, Icon Sets, and Audio, Other UX Design Elements

Before you present stock photo options to your clients (i.e. during the kickoff or early on in the project), explain the difference betweeen free and paid stock photos, and discuss quality and relevancy of stock photo choices.

Here are a few options for free stock photos. We can also use them as placeholders while we wait for the client to source the final photos (assuming they are doing the sourcing, instead of us):

**Free Stock Photos**:
- [http://www.sitebuilderreport.com/stock-up](http://www.sitebuilderreport.com/stock-up)
- [http://foodiesfeed.com/](http://foodiesfeed.com/)
- [http://startupstockphotos.com/](http://startupstockphotos.com/)
- [http://www.imcreator.com/free](http://www.imcreator.com/free)
- [http://nos.twnsnd.co/](http://nos.twnsnd.co/)
- [https://unsplash.com/](https://unsplash.com/)

### Animations

Animations can take your design to the next level, so we encourage using them to enhance your user's experience. (That said, if they put you over budget, it's probably best to keep it simple and leave animations out.)

To ensure that animations can be done within budget, **consider them ahead of time.** (Sidenote: You can always work with James or your Project Manager to get more budget for a cool feature you dreamed up! But we do try to include animations in the estimate if we know about them.)

Work closely with your developer on animations. Discuss ideas first. Once you come up with an animation, you can create a visual to cement the concept in everyone's mind using:

1. Write a detailed, specific text description. Outline the transition timing in text.
2. [Origami + Quartz (Origami)](https://facebook.github.io/origami/)
3. [After Effects (GIFs)](http://www.adobe.com/products/aftereffects.html)
4. [Framer](http://framerjs.com/)
5. [Actually coding it](http://codepen.io)

---

Our next service is [Development&#8594;](/Our_Process/Our_Services/Development).