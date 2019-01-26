---
date: "2019-01-25"
title: "Labs Week 3"
category: "Lambda Labs"
---

## Individual Accomplishments

[@zacharyarney](https://github.com/zacharyarney)

[Contribution Graph](https://github.com/Lambda-School-Labs/labs9-team-home/graphs/contributors?from=2019-01-18&to=2019-01-26&type=c 'Github Repository Contribution Graph')

Last week was the end of broad brush strokes on the project. This week we're starting to hone things in. I spent some time this week fine tuning our FilePond image upload widget. Last week it was working but I allowed a user to upload any type and size of photo they could want. This week I added constraints to the allowed file types so that only images can be uploaded and large images are resized. I also got our non-functioning settings page functioning and connected to the back end.

## Whiteboarding Session

- [Jan 24 Whiteboarding Session](https://www.youtube.com/watch?v=eezohdZZWYE&t=1s)

## Tasks Pulled

### Front End

- Image upload constraints
  - [Trello link](https://trello.com/c/K1bG7oUw/94-image-upload-constraints)
  - [Github link](https://github.com/Lambda-School-Labs/labs9-team-home/pull/114)
- Connecting settings page to back-end
  - [Trello link](https://trello.com/c/zUffKRE4/4-user-settings-page)
  - [Github link](https://github.com/Lambda-School-Labs/labs9-team-home/pull/134)

## Detailed Analysis

This week one of my tasks was to connect the user settings page to our backend api. There were two challenging parts to this task: working on pre-existing code, and using Apollo to make a GraphQL mutation from the front end. GraphQL is still pretty new to me. We diceded to use it because of it's ability to give you only the information you need from your database, and so far it's been really intuitive to set up on the back end. This was my first try at interacting with it from the front end. With Apollo, GraphQL queries and mutations are actually components that you wrap your other components in. The mutation is defined outside of the component and actually resembles the schema pretty closely. The mutation component takes in the mutation as an argument to a render prop along with an object that contains the returned data from the mutation. The function is called inside the component (in this case, in the onSubmit prop of our form) and takes in an object with all the information to be mutated. So when our form is submitted the pre- defined function is triggered and updates our user accordingly.

Mutation defined<br />
![Mutation defined](https://www.dropbox.com/s/u9bmnb14e2xl8dg/Screen%20Shot%202019-01-25%20at%2011.54.21%20PM.png?raw=1 'Mutation defined')

Mutation component with updateUser function called in form onSubmit<br />
![Mutation component with updateUser function called in form onSubmit](https://www.dropbox.com/s/sj855x1oeto423e/Screen%20Shot%202019-01-25%20at%2011.51.56%20PM.png?raw=1 'Mutation component with updateUser function called in form onSubmit')

updateUser mutation in the User resolver file<br />
![updateUser mutation in the User resolver file](https://www.dropbox.com/s/jgar1mrc7nw5iy7/Screen%20Shot%202019-01-25%20at%2011.56.24%20PM.png?raw=1 'updateUser mutation in the User resolver file')

## Feature Complete: Cohesion

It's interesting how simply adding some global styles can make a seemingly scattered project start to feel finished. You spend weeks looking at the code and getting used to the quirks and bugs in each feature. Each page has it's own set of problems and personality. But all of the patchwork and scaffolding is so easily hidden behind a consistent color palette and a font. 

Something I had to get used to this week was working on someone else's code. Until now, we (or maybe just I) had been mostly modular, working on our separate features and components. But this week I started working on the settings page, which I did not build. I found that working on someone else's code is kind of a different and maybe more challenging task than simply writing it. It forced me to think differently and work in ways that I normally wouldn't because I had to work within the logic of the framework built by my teammate. Right now, while the UI is approaching a state of cohesion, the underlying code is still pretty inconsistent. We all have different styles for writing code. But now that all the pieces are in place and we all start working on top of each other's code, I think everything will start to become more homogenous.

## Weekly Milestones

https://team-home.netlify.com/

- Auth0 integrated
- Stripe integrated
- Image upload integration via FilePond and hosting on Cloudinary
- Sendgrid integrated for email notifications
- Twilio integrated for text notifications
- Users can create messages with photos and can subscribe to threads, add comments, likes
- Users can update their information
- Users can join, add and leave teams
