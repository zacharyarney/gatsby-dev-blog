---
date: "2019-02-01"
title: "Labs Week 4"
category: "Lambda Labs"
---

## Individual Accomplishments

[@zacharyarney](https://github.com/zacharyarney)

[Contribution Graph](https://github.com/Lambda-School-Labs/labs9-team-home/graphs/contributors?from=2019-01-19&to=2019-01-27&type=c 'Github Repository Contribution Graph')

<!-- Provide a paragraph (5-8 sentences) summarizing the work you did this week, the challenges you faced, the tools you used, and your accomplishments. -->
This week was all about pushing up a product. Something you'd be willing to put out to real users. I think in most respects we were able to accomplish that goal. Functionally the app is doing everything it should. But the styling still needs some work to look polished. We implemented Material UI this week to help with uniformity and polish. I think it helped in that way, but it also took some time to figure out and introduced some bugs we had to fix.

## Whiteboarding Session

- [Jan 31 Whiteboarding Session](https://youtu.be/YqpooUQFnaQ)

## Tasks Pulled

### Front End

- Connect settings page to back end
  - [Trello link](https://trello.com/c/K1bG7oUw/94-image-upload-constraints)
  - [Github link](https://github.com/Lambda-School-Labs/labs9-team-home/pull/143)
- User avatar upload
  - [Trello link](https://trello.com/c/VuM6ToP8/38-image-hosting)
  - [Github link](https://github.com/Lambda-School-Labs/labs9-team-home/pull/150)
- Color variables
  - [Trello link](https://trello.com/c/vElZgIRq/134-color-variables)
  - [Github link](https://github.com/Lambda-School-Labs/labs9-team-home/pull/155)
- Material UI/styled-components scope issue bug fix
  - [Trello link](https://trello.com/c/aqtLFHVX/133-bugfix-material-ui-styled-components-scope-conflict)
  - [Github link](https://github.com/Lambda-School-Labs/labs9-team-home/pull/158)
- Unbreak filepond styling
  - [Trello link](https://trello.com/c/MqXaPeFt/132-bugfix-unbreak-filepond-styling)
  - [Github link](https://github.com/Lambda-School-Labs/labs9-team-home/pull/161)
- Settings page styling
  - [Trello link](https://trello.com/c/zUffKRE4/4-user-settings-page)
  - [Github link](https://github.com/Lambda-School-Labs/labs9-team-home/pull/172)
- Remove Home button and add Logout button to Navbar
  - [Trello link](https://trello.com/c/3GElKTiq/70-nav-bar)
  - [Github link](https://github.com/Lambda-School-Labs/labs9-team-home/pull/175)

## Detailed Analysis

<!-- Pick one of your tickets and provide a detailed analysis of the work you did. This should be approximately 1/4 page of text, and at least three screenshots. -->
I did a lot of styling this week, as did the rest of the team. Since we were styling as a group we decided on some guidelines to help us keep things consistent. I created a variables file for our color palette to allow us to easily plug in the human-readable variables into our styles instead of hex or RGB values and to allow us to change the colors from one convenient spot if we choose to do so later on. I created variables for the color palette inside of an object and then a second object containing variables for all of the common components that would be used. The second objects variables referenced the colors from the palette. This way, if we need to change any of the colors, we can just change them in the palette object and any elements in the element object using that color will change. If the name of the color variable changes we can just change it in the elements object instead of having to hunt down every instance of it across the project.

We also implemented Material UI this week. I am new to Material and Kind of had to learn it on the fly. It works pretty seamlessly with styled-components--all you do is plug the Material element into the definition of the component. The only issue is that Material UI is designed so that all of it's styles are inserted last in the compiled CSS document. It does this to preserve its default styling but this makes it difficult to overwrite with styled components because the Material styles have a more specific scope. So remedy this, there is a tool built into Material that allows you to pick an insertion point for Material's styling in the `<head>` of your index.html file.


Color variables<br />
![Color variables](https://www.dropbox.com/s/7sfca1z8crfy7xo/Screen%20Shot%202019-02-01%20at%208.55.51%20AM.png?raw=1 'Color variables')

Styling a Material UI element with overwritten animations<br />
![Styling a Material UI element with overwritten animations](https://www.dropbox.com/s/xiwnzh3dn65rx3k/Screen%20Shot%202019-02-01%20at%208.56.36%20AM.png?raw=1 'Styling a Material UI element with overwritten animations')

Material UI JSS insertion point<br />
![Material UI JSS insertion point](https://www.dropbox.com/s/7qaa9dfgvors2is/Screen%20Shot%202019-02-01%20at%208.57.18%20AM.png?raw=1 'Material UI JSS insertion point')

## Presentation and Making a Finished Product

<!-- Description from labs training kit page for the week -->
This week the whole team shifted to styling. Up to this point, styling had been delegated primarily to a single person. With five people working simultaneously on different parts of the app, uniformity was an issue that needed to be addressed and we did that in a couple of ways. The first part was to create a color palette for everyone to use. We formalized this by creating a file with variables for all the colors that we can just import and plug in to any of out styled-components files. The second part was to implement the Material UI styling library into our project for common elements like buttons, tabs and inputs. With this we were able to add styling independently in a sort of paint-by-numbers fashion and achieve a uniform look for the site.

## Weekly Milestones

https://team-home.netlify.com/

- All features functional
- Styling getting close to done
- Material UI implemented
- Some bugs fixed
- Consistency between Web and iOS
