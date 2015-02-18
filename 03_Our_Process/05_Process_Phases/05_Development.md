## Getting Started

At the outset of each project, download the [Front-end Starter Kit](https://github.com/thephuse/starter-kit/archive/master.zip) to provide a lean setup for your JavaScript & CSS preprocessor and minification tasks. [Read the instructions](https://github.com/thephuse/starter-kit/blob/master/README.md) to get up and running.

The Starter Kit will auto-update JS and CSS in your browser window upon file save, speeding up your workflow throughout the project.

## Preprocessors

We prefer to use preprocessors instead of straight html and css.

Never use a preprocessor that compiles on-server unless dealing with a client who requests it. Always use a [Grunt](http://gruntjs.com/) task (or similar) to process your raw files into browser-legible CSS, HTML & JavaScript.

## HTML

For rails projects, we often use [Slim](http://slim-lang.com/) or [Haml](http://haml.info/), which are HTML preprocessors. For NodeJS projects, [Jade](http://jade-lang.com/) is a good alternative to Haml.

Regardless of which markup language you’re using, child elements should be indented a level deeper than their parent. This alleviates the need to add comments after close tags in messier languages.

## CSS

[Sass](http://sass-lang.com/) or [LESS](http://lesscss.org/) are excellent CSS preprocessors, and either can be used. SCSS (Sassy CSS, a Sass syntax) is recommended due to its flexibility advantages over LESS, and its syntactical similarity to raw CSS. The dev starter kit utilises [Compass](http://compass-style.org/), a fully-featured mixin library for Sass/SCSS.

## JavaScript

All JavaScript should follow an AMD or CommonJS pattern. We recommend using [Browserify](http://browserify.org/), which is included in the starter kit. Browserify allows client-side use of the `require()` pattern enforced by NodeJS, and offers CoffeeScript and minification options.

Resources:

- [Article to fix JSDOM on Windows 8 for testing](http://marisks.net/2014/02/13/installing-jsdom-on-windows-8/)

## Organization

Our clients are like our users in that they tend to view websites and applications in terms of pages and not in terms of modules. Since the majority of our work is modular, their feedback may need to be broken down by module, and preferably broken down even further into actionable tasks.

## Code formatting

Unless otherwise instructed, follow GitHub’s standards for code formatting.

- [CSS style guide](https://github.com/styleguide/css) 
- [HTML style guide](https://github.com/styleguide/templates)
- [JS style guide](https://github.com/bevacqua/js)

## Browser support

We support the following browsers, unless otherwise specified in a project's SOW or requested by a client:

*Browser support listed below current at the time of writing. The onus is on the developer to check the current stable version of each listed browser.*

Desktop (current -> 2 versions back)
- Chrome: 40, 39, 38
- Safari: 7.1, 7.0, 6.2
- Firefox: 35, 34, 33
- Opera: 27, 26, 25

Desktop (explicit support)
- IE: Project Spartan, 11, 10, 9 (with graceful degradation)

Mobile (current -> 2 versions back)
- iOS Safari: 8, 7.1, 7
- iOS Chrome: 40, 39, 38
- Android Chrome: 40, 39, 38
- Android Stock Browser: Lollipop, KitKat, Jellybean

Mobile (explicit support)
- Windows Phone: OS 8.1, IE 11
- Windows Phone: OS 7, IE 10

Mobile (not supported)
- Opera Mini: Unsupported
- Blackberry Browser: Unsupported

## Setting Up Ruby on Rails Projects

When working on a new Rails project, you will find instructions to set up a local environment in the README.md file in github.

If you run into trouble setting it up, contact the backend developer assigned to your project. If you don’t know who the developer is yet, ask your Project Manager!

Each Rails shop has different guidelines and requirements for working with them.

## Website Checklist for Developers

Here's a checklist you can use to make sure you've hit all the QC basics for a standards-compliant website:

1. Validate HTML - Use W3's HTML validator or a similar tool to validate each page’s HTML
2. Validate CSS - Use W3's CSS validator or a similar tool to validate the project’s CSS
3. Lint JavaScript - Use jshint or similar tools to lint and hint the project’s JavaScript
4. Fix broken links - Use W3's link checker or a similar tool to check for broken links. If you have broken links due to incompletion of the project, add the following comment or something similar on the line preceding the anchor element: <!— TODO fix broken link —>
5. Test all pages in all supported browsers - Use your installed applications or BrowserStack to check each page in Safari, Opera, Chrome, Firefox, Internet Explorer 9, and 10 as well as any other browsers required by the project
6. Optimize images - After some comparisons, I highly recommend Kraken for image files under 1mb. In my tests, Kraken trimmed file size by ~2x what the competitors did
7. PageSpeed Recommendations - Use PageSpeed Insights to see suggestions for improving speed and performance
8. Add a robots.txt file
9. Add a sitemap.xml file (or through a plugin)
10. Add Google Analytics and ask the clients to set up their Google Webmaster stuff
11. Ask clients about additional meta tags
12. For WordPress, add Google XML Sitemaps and Stealth Login
13. Ask client if there are any additional steps(such as adding Google+ codes, Open Graph info, etc) they would like us to take

## <a name="Technical_Debt"></a>Technical Debt and How to Avoid It

**Technical debt. We’ve all had to deal with it, and we’re all guilty of creating it.**

Five principles should be considered to help reduce technical debt in your own code.

- Performance
- Modularity
- Reusability
- Brevity
- Documentation

Every one of us has stumbled into a project that’s perplexed us and demanded a long lead time just to understand the basics of it. Here are some guidelines on how to avoid just that. The following can be used as a formal code review checklist during dev audits and post-project code reviews.

If you have any questions, ask Matt and he’ll work with the development team to come up with a group consensus, based on best practices, to use going forward.

- Ensure your files are laid out in a logical manner: pick a directory, file and module structure and stick with it.

- Adopt a strictly modular, decoupled approach with your JS and CSS.

  - Always use CommonJS or AMD with JavaScript.

  - Build reusable modules. Just because it’s needed in one area now, doesn’t mean it won’t be needed again down the line.

  - Use functional libraries in JavaScript. Functional programming can not only offload a lot of drudgery to functional libraries—it also encourages canonical treatment of functions, makes for brevity in code, and is usually already very well documented by the library of choice.

  - Pick the right JavaScript libraries for the application and keep a record of the ones used, as well as the location of their documentation either inline (usually this is recorded in their script comments) or in your readme file.

- Use objects (classes/prototypes) and namespaces if the language you’re coding in permits it. Inheritance will allow other developers to extend or replace entire portions of your code, rather than having to sift through reams of it just to substitute a function or two.

- Use a package manager (e.g. NPM or Bower) if your app has lots of dependencies.

  - Use “\*” in package.json if version is of no consequence and the dependency will not introduce breaking API changes in a future version.

  - Browserify can haul scripts out of the node_modules folder, that have been downloaded via NPM. This includes jQuery (albeit with a shim)!

- Lint your JavaScript. Browserify will do this for you by catching any errors. If you’re not 100% sure-footed with your JavaScript, throw in JSHint or similar. Always use strict JavaScript by include ‘use strict’; within your code. Google the differences between Strict and Sloppy JavaScript if unsure.

- Ensure that transpiled files carry appropriate file extensions. By way of example, do not suffix SCSS with .sass and do not keep SCSS files witin a /sass/ folder. Use canonical extensions, e.g. .coffee instead of .cs or .coffeescript.

- Document everything. Do not rely on word of mouth or otherwise to transfer knowledge of the project from you to any poor developer who might have to pick it up in the future.

  - Pick a documentation style and run with it. This can be JSDoc or otherwise, depending on the client and the work to hand.

  - For JS:
      - CoffeeDoc works great with CoffeeScript, and follows Python’s docstring syntax.

      - JSDoc is a great choice for larger projects and encourages developers to build in a type-safe manner.

      - If you’re not a writer, just include the briefest explanation of every function with a variable rundown. JSDoc is great for this—it pretty much writes your documentation for you.

  - For CSS:

      - Document any snags, browser inconsistencies, effects (transitions; animations) or foreseeable issues inline within your code. Ensure your naming scheme indicated what the CSS module styles, unambiguously.

  - For HTML:
  
      - If using an inline scripting language like PHP, or a transpiler like Jade, be sure to comment your markup comprehensively—comments can be automatically parsed out of rendered HTML.

  - For PHP:

      - Use phpDocumentor or similar; or just ensure that your functions are documented with comprehensive notes concerning the number, types and compulsoriness of arguments. This is especially important for documenting long, unordered collections of functions, e.g. those contained within a Wordpress theme’s functions.php.

- When quoting for a project, come in high if you can. You will never expend less time than quoted for.

  - Clients are usually amenable to the idea of technical debt avoidance. They are paying very slightly more for a product in order not to have to pay a disproportionately high fee down the line, when either different developers need to take up the slack or their site is due for updates from the new developer, who did not produce work in a clearly-commented, modular and reusable fashion. Clients need to understand the true price of good development.

  - Any extra development time should be spent on following the guidelines above, to ensure the quality of your codebase, as well as polishing the site/application and tweaking performance.

  - For more on how to estimate on projects, [Technical Presales is covered here#8594;](/Our_Process/Technical_Presales).

---

Our next service is [Print&#8594;](/Our_Process/Our_Services/Print).