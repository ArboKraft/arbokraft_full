---
#
# Use the widgets beneath and the content will be
# inserted automagically in the webpage. To make
# this work, you have to use › layout: frontpage
#
layout: frontpage
header:
  image_fullwidth: start-header.png
widget1:
  title: "Exercises"
  url: '/exercises/'
  image: '/images/exercises/widget.png'
  text: ''
widget2:
  title: "Resources"
  url: '/resources/'
  image: '/images/resources/widget.png'
  text: ''
widget3:
  title: "Blog"
  url: '/blog/'
  image: '/images/blog/widget.png'
  text: ''
#
# Use the call for action to show a button on the frontpage
#
# To make internal links, just use a permalink like this
# url: /getting-started/
#
# To style the button in different colors, use no value
# to use the main color or success, alert or secondary.
# To change colors see sass/_01_settings_colors.scss
#
#callforaction:
#  url: https://tinyletter.com/feeling-responsive
#  text: Inform me about new updates and features ›
#  style: alert
permalink: /index.html
---