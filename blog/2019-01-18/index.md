---
date: "2019-01-18"
title: "Labs Week 2"
category: "Lambda Labs"
---
## Individual Accomplishments

[@zacharyarney](https://github.com/zacharyarney)

[Contribution Graph](https://github.com/Lambda-School-Labs/labs9-team-home/graphs/contributors 'Github Repository Contribution Graph')

<!-- Provide a paragraph (5-8 sentences) summarizing the work you did this week, the challenges you faced, the tools you used, and your accomplishments. -->

This week was a mixture of bug fixes and adding features to Team Home. The challenge really came in prioritizing bugs and trying to implement features into an app that neither complete nor fully working. My biggest contribution this week was probably integration of image hosting with Cloudinary's cloud service. Getting the app to talk to Cloudinary proved a bit of a struggle, but once they were connected, integration into the app was almost as simple as plugging it in.

## Tasks Pulled

### Back End

- Updates backend readme with info on using Auth0, Sendgrid Twilio locally #64
  - https://github.com/Lambda-School-Labs/labs9-team-home/pull/64
  - https://trello.com/c/4hssRP3t/13-readmes-front-back-readme-feature-checklist

### Front End

- Feature/nav #67 (rolled in with #73 to master)
  - https://trello.com/c/3GElKTiq/70-nav-bar
  - https://github.com/Lambda-School-Labs/labs9-team-home/pull/67

- Feature show messages #75
  - https://trello.com/c/VuM6ToP8/38-image-hosting
  - https://github.com/Lambda-School-Labs/labs9-team-home/pull/75

### Misc.

- Adds missing EoF newlines in .json files #51 (included in #22)
  - https://github.com/Lambda-School-Labs/labs9-team-home/pull/51

- Feature/general readme #41
  - https://trello.com/c/4hssRP3t/13-readmes-front-back-readme-feature-checklist
  - https://github.com/Lambda-School-Labs/labs9-team-home/pull/41


## Detailed Analysis

<!-- Pick one of your tickets and provide a detailed analysis of the work you did. This should be approximately 1/4 page of text, and at least three screenshots. -->
I spent a fair amount of time this week working on integrateing the image hosting feature into our app. We decided to go with Cloudinary for our image hosting. Cloudinary offers a widget that you can plug into your application for image uploads. It allows users to upload a variety of files from a number of sources. I decided not to go with it in the end, mostly because of the form factor. It's a rather large and kind of ugly thing that doesn't really match the aesthetic of our app and I wanted somthing that would feel more seamless. Initially I tried using a library called [React Dropzone](https://react-dropzone.netlify.com/) which allows for some simple drag and drop files to upload, but was unable to get it to talk with Cloudinary. Cloudinary requires a specific set of form data to be sent along with the photo, and the solution I found to be able to send this data and return the required url was a library callde [FilePond](https://pqina.nl/filepond/). The benevit of useing FilePond with react is that you can customize it's send process inside the component in your render, so it's self contained and doesn't rely on methods passed in through props. I was able to customize what was being sent and interact with Cloudinary via XML Http requests (for some reason I was unable to make requests to Cloudinary using axios). Once the connction with Cloudinary was made, Charles and I were able to plug it into the component for adding messages and add the returned image url to the message data with a GraphQL mutation. 

FilePond Component with form data<br />
![FilePond Component with form data](https://www.dropbox.com/s/dg2imkq4b2h3ob9/Screen%20Shot%202019-01-18%20at%209.10.58%20AM.png?raw=1)

XML POST request<br />
![XML POST request](https://www.dropbox.com/s/kr4py9q9exyec3x/Screen%20Shot%202019-01-18%20at%209.11.41%20AM.png?raw=1)

Getting the response from Cloudinary<br />
![Getting the response from Cloudinary](https://www.dropbox.com/s/78fc2crad0kklc0/Screen%20Shot%202019-01-18%20at%209.19.17%20AM.png?raw=1)

## Experiences Forming A Team

<!-- Description from labs training kit page for the week -->
This week was a bit of a scramble. We had a difficult MVP to meet--integrating all third-party APIs and services and making a meaningful connection between front and back end. For the most part we each worked individually on our respective projects but when trouble came up, we were able to work together to fix and figure out problems. Because there was so much to be done, communication was key to making sure all these different elements fit together. Image integration was probably the easiest to roll into the app because, once the connection with Cloudinary was made, the component was completely modular. In the comming weeks it should be able to be integrated with other parts of the app, like setting user avatars, with realtive ease. 

## Weekly Milestones

<!-- insert stuff here -->
Front end deployment with image hosting:<br/>
https://team-home.netlify.com/home
