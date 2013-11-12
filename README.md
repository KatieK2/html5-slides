#HTML5 Slide Template
[Originally from Google IO](http://code.google.com/p/io-2012-slides), and with an [Apache 2.0 license](http://www.apache.org/licenses/LICENSE-2.0).

**[Live Demo here](https://rawgithub.com/KatieK2/html5-slides/master/template.html)**

This is slideshow / presentation framework (built with HTML5, CSS and JS) which runs in a variety of modern web browsers.  Here's a sampling of features:

 * Slides and images adjust to screen-width.
 * Keyboard control for navigation and effects.
 * In-slide revealable elements.
 * Well designed code blocks with code highlights.
 * Togglable speaker notes.

## Running the slides

The slides can be run locally from `file://` making development easy :)

Press Enter, space, right arrow to advance; Backspace, left arrow to go back.

Enter full-screen mode (F11 or Shift-Command-F) before presenting.

You should be able to press Ctrl+R/F5 at any time to refresh without losing your place in the presentation.

If an iframe steals your focus and you can’t advance any more, please click outside the slide on the background to give the focus back to the presentation. 

## Configuring the slides

Much of the deck is customized by changing the settings in [`slide_config.js`](slide_config.js).
Some of the customizations include the title, Analytics tracking ID, speaker
information (name, social urls, blog), web fonts to load, themes, and other
general behavior.

### Customizing the slide titles

The bottom of the slides include `title` by default. If you'd like to change this, please update the variable
 `$title: 'title';` in [`/theme/scss/default.scss`](theme/scss/default.scss) 
or change `content: "#yourhashtag";` [`/theme/css/default.css`](theme/scss/default.css).

See the next section on "Editing CSS" before you go editing things.

## Editing CSS

[Compass](http://compass-style.org/install/) is a CSS preprocessor used to compile
SCSS/SASS into CSS. We chose SCSS for the new slide deck for maintainability,
easier browser compatibility, and because...it's the future!

That said, if not comfortable working with SCSS or don't want to learn something
new, not a problem. The generated .css files can already be found in
(see [`/theme/css`](theme/css)). You can just edit those and bypass SCSS altogether.
However, our recommendation is to use Compass. It's super easy to install and use.

### Installing Compass and making changes

First, install compass:

    sudo gem update --system
    sudo gem install compass

Next, you'll want to watch for changes to the exiting .scss files in [`/theme/scss`](theme/scss)
and any new one you add:

    $ cd io-2012-slides
    $ compass watch

This command automatically recompiles the .scss file when you make a change.
Its corresponding .css file is output to [`/theme/css`](theme/css). Slick.

By default, [`config.rb`](config.rb) in the main project folder outputs minified
.css. It's a best practice after all! However, if you want unminified files,
run watch with the style output flag:

    compass watch -s expanded

*Note:* You should not need to edit [`_base.scss`](theme/scss/_base.scss).

##### Running from a web server

If at some point you should need a web server, use [`serve.sh`](serve.sh). It will
launch a simple one and point your default browser to [`http://localhost:8000/template.html`](http://localhost:8000/template.html):

    $ cd io-2012-slides
    $ ./serve.sh

You can also specify a custom port:

    $ ./serve.sh 8080

##### Presenter mode

The slides contain a presenter mode feature (beta) to view + control the slides
from a popup window.

To enable presenter mode, add `presentme=true` to the URL: [http://localhost:8000/template.html?presentme=true](http://localhost:8000/template.html?presentme=true)

To disable presenter mode, hit [http://localhost:8000/template.html?presentme=false](http://localhost:8000/template.html?presentme=false)

Presenter mode is sticky, so refreshing the page will persist your settings.
