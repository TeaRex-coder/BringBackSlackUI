# Bring Back Slack UI

In Fall 2023, Slack received a UI update which removed the ability to customize theming using the 9-property colour schemes. This project aims to bring it back!

The colour schemes involved the following properties:

- Column BG
- Active Item
- Active Item Text
- Hover Item
- Text Color
- Active Presence
- Mention badge
- Top Nav BG
- Top Nav Text

## Project Status

This project is currently a work-in-progress, please check back soon for updates!

### Current

I am working through writing the CSS to colour the individual elements.

### Future Plans

This is a blur for me right now but here are some thoughts on what I might do:

- Browser extension for Slack web
- Custom Slack Desktop app using something like [Nativefier](https://github.com/nativefier/nativefier) or something still being worked on
- CSS injections like what [BetterDiscord](https://github.com/BetterDiscord/BetterDiscord) for theming the Discord electron client

## Development

### Environment Setup

If you need to have a look at the old UI, follow [this helpful guide](https://gist.github.com/Kenny-MWI/6b1a88ad38b5ffef347527a82becf054) from [Kenny-MWI](https://github.com/Kenny-MWI).

### Understanding Theme Properties

In the old first-party Slack UI, the sidebar can be customized with 9-property themes using HEX codes separated by commas (no spaces) This project replicates this behaviour as best as possible. You can use a series of 8 or 10 HEX codes. Here is the behaviour of each:

**8-Property Theme**

Example: `#FFFFF0,#FFFFF1,#FFFFF2,#FFFFF3,#FFFFF4,#FFFFF5,#FFFFF6,#FFFFF7`

Expected behaviour:
`#FFFFF0,#FFFFF1,#FFFFF2,#FFFFF3,#FFFFF4,#FFFFF5,#FFFFF6,#FFFFF7,#FFFFF0,#FFFFF5`

- Column BG: `#FFFFF0`
- Active Item: `#FFFFF1`
- Active Item Text: `#FFFFF2`
- Hover Item: `#FFFFF3`
- Text Color: `#FFFFF4`
- Active Presence: `#FFFFF5`
- Mention badge: `#FFFFF6`
- Top Nav BG: `#FFFFF7`
- Top Nav Text: `#FFFFF0`

> With 8-property themes, Slack converts them to a 10-property theme. The last 2 properties are collected from the 1st and 6th properties. Then only the first 9 properties are used to theme the Slack sidebar.

**10-Property Theme**

Example: `#FFFFF0,#FFFFF1,#FFFFF2,#FFFFF3,#FFFFF4,#FFFFF5,#FFFFF6,#FFFFF7,#FFFFF8,#FFFFF9`

Expected behaviour:
`#FFFFF0,#FFFFF1,#FFFFF2,#FFFFF3,#FFFFF4,#FFFFF5,#FFFFF6,#FFFFF7,#FFFFF0,#FFFFF5`

- Column BG: `#FFFFF0`
- Active Item: `#FFFFF1`
- Active Item Text: `#FFFFF2`
- Hover Item: `#FFFFF3`
- Text Color: `#FFFFF4`
- Active Presence: `#FFFFF5`
- Mention badge: `#FFFFF6`
- Top Nav BG: `#FFFFF7`
- Top Nav Text: `#FFFFF0`

> With 8-property themes, the last 2 properties are replaced with the 1st and 6th properties. Then only the first 9 properties are used to theme the Slack sidebar.

**Other**

Themes with 9-properties, less than 8, or more than 10 aren't accepted.

### How Theme Properties Affect Slack UI

This section is TBD. I will first knock release the first version and then include examples of how the 9 properties affect both the old and new UI.
