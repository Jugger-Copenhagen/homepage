# Jugger Copenhagen homepage

Based on Hugo.

## Global TODO

- Add more SEO information to website headers.
- Style Google Calendar plugin to match remaining pages.
- Danish language support.

### Calendar

The non-Google fancy calendar is made with [FullCalendar](https://fullcalendar.io), an almost plug-and-play JS plugin. The calendar is implemented as the {{< calendar >}} shortcode that inserts the required HTML etc. The JS plugin is loaded in custom_head.html. Configuration options for the calendar are specified in the JavaScript code in the shortcode.

#### Styling

By default the calendar matches the theme relatively well, but to further improve it you can adjust the JS options or write custom CSS properties: [CSS Customization](https://fullcalendar.io/docs/css-customization)

## Styling

Most of the styling is provided by the hugo-scroll theme that is embedded as a github subrepository. However, we do a few custom styling things, which are visible in assets/css:

* variables.scss contains all of the "brand" colors that we use for Skøll; it defines the blues, red, yellow, and charcoal that are part of our logo and used across the site. This is also the file that controls which colors are used for the dark/light portions of the site, and more or less the backbone of everything getting rendered by the hugo-scroll theme.
* fonts.css includes the Norse and Norse Bold fonts that we use to render Skøll

In layouts/partials/customhead.html, we have also defined some Skøll-specific stuff, which lets us actually render the Skøll shortcode and color links differently across the dark and light bands of the homepage.


## Pages

### Homepage

Everything that appears on the homepage is a file in content/<langcode>/homepage : they are ordered based on the "weight" given to them in their respective files.

#### Navigation bar

This is auto-generated by Hugo based on the "header_menu" and "navigation_menu" things set up in the files in the homepage/ folder.

#### Banner and Logo

The banner image is located in `assets/images/runin.jpg`. The logo is `assets/images/skøll logo only.png`.

#### Main content

The main content is, as noted, generated and arranged based on the files in content/<langcode>/homepage.

### Tournament list

The tournament list is generated based on things that are in the content/<langcode>/tournament folder. The markdown files in there need to follow the pattern of the 2025DUI.md file, which has begin and end times, name, shortname, etc. Each tournament displays in a short way (on the main page) and in a long way (on the dedicated tournament page).

## Shortcodes

Several custom shortcodes are used for rendering fun content in layouts/shortcodes:

* {{< skøll >}} can be used anywhere _except titles_ to render Skøll in the Norse font. It can be called as {{< skøll red >}} (or lightblue, darkblue, yellow, charcoal) to be colored as requested, otherwise it will be the same color as the surrounding font.
* {{< gcal >}} will embed our google calendar.
* {{< svg SVGNAME >}} will embed a little SVG. The available SVGs are in static/images, and can be called as {{< svg chase >}} to embed silhouette_chase.svg

## SEO

In hugo.toml, there are some SEO things defined (keywords, etc.)

### Hugo resources

- [Hugo SEO Best Practices](https://cloudcannon.com/tutorials/hugo-seo-best-practices/)

# How to install and run

install hugo -> https://gohugo.io/installation/macos/
 (e.g., `$ brew install hugo`)

build with hugo -> `$ hugo`

test run -> `$ hugo server`
