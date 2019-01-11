---
date: "2019-01-11"
title: "Labs Week 1"
category: "Lambda Labs"
---
## Individual Accomplishments

[@zacharyarney](https://github.com/zacharyarney)

[Contribution Graph](https://github.com/Lambda-School-Labs/labs9-team-home/graphs/contributors 'Github Repository Contribution Graph')

<!-- Provide a paragraph (5-8 sentences) summarizing the work you did this week, the challenges you faced, the tools you used, and your accomplishments. -->

This week included a lot of planning and preparation. The team spent the first two days putting together a design doc and planning the tech stack we wanted to use for this project. Once we had the plans laid, I helped along with the entire web team to set up our MongoDB server and GraphQL/Apollo api, and later worked with Blake and David to complete the api. The biggest challenge in this was the learning process for MongoDB, GraphQL and Apollo. All are new to me and I still feel like I'm wrapping my head around GraphQL in particular. MongoDB is a pretty intuitive database structure that I think works really well in combination with GraphQL to make our backend really flexible. I also spent some time this week setting up Cloudinary for image hosting which we will be implementing in the future.

## Tasks Pulled

### Back End

- Set up MongoDB database models and graphql API
  - https://trello.com/c/aRbquWgt/9-database
  - https://github.com/Lambda-School-Labs/labs9-team-home/pull/7
- Add User resolver, update tag resolvers and update schemas for mutations
  - https://trello.com/c/YtOjDA9C/30-set-up-api
  - https://github.com/Lambda-School-Labs/labs9-team-home/pull/16
- Add config directory
  - https://trello.com/c/YtOjDA9C/30-set-up-api
  - https://github.com/Lambda-School-Labs/labs9-team-home/pull/17

## Detailed Analysis

<!-- Pick one of your tickets and provide a detailed analysis of the work you did. This should be approximately 1/4 page of text, and at least three screenshots. -->
The api was really inteteresting to work on. My only previous experience is with RESTful apis and GraphQL works very differently. The first step to creating a GraphQL api is to create schemas for the data you're retrieving from the database. In this case, the schemas very closely resembled the data models in our MongoDB database. They define data types. Not a direct copy/paste from MongoDB but the JSON-esque structure of GraphQL is pretty close. Also included in these schemas are models for any queries or mutations you intend on using in the api. Queries are basically the GraphQL equivalent of a GET request in a RESTful api, and mutations cover any requests that might alter (mutate) the data like POST, PUT or DELETE. The final part of the schema is to allow the actual queryies and mutations just defined. After creating the schemas we had to create what are called resolvers. Resolvers are basically the functions that make the actual queries and mutations of the database based on the schemas

GraphQL schema data model and typedefs<br />
![GraphQL schema data model and typedefs](https://www.dropbox.com/s/mf7ndp1k5e7ivpx/Screen%20Shot%202019-01-11%20at%207.15.08%20AM.png?raw=1)

GraphQL query and mutation typedefs<br />
![GraphQL query and mutation typedefs](https://www.dropbox.com/s/p74d5iwx5da2h5w/Screen%20Shot%202019-01-11%20at%207.15.31%20AM.png?raw=1)

GraphQL resolvers for query and add comment mutation<br />
![GraphQL resolvers for query and add comment mutation](https://www.dropbox.com/s/3oyhn65qu2ofozr/Screen%20Shot%202019-01-11%20at%207.12.47%20AM.png?raw=1)

## Experiences Forming A Team

<!-- Description from labs training kit page for the week -->
This week we began learning to work on a team. Until now my work at Lambda has been almost entirely solitary and learning to work on a team with others is kind of a jarring process. It can be difficult to both get to know your teammates and try to accomplish tasks with them in tandem. A lot of what makes a good team seems to be familiarity paired with each individuals ability to be dynamic and adjust to changes quickly. While this week started off kind of slow in the planning phase, I think that working on the backend together was a great team building exercise. GraphQL was new tech to most of us and learning it together, starting on the same page, was a great way to jump into this project. Things I want to work on moving forward are organization and planning. I find I have a lot of anxiety about stepping on my teammate's toes or doing redudndant or unnecessary work and I think developing a clear outline for what needs to be done will be a big help in making our team more productive as a whole.

## Weekly Milestones

<!-- insert stuff here -->
Front end deployment:<br/>
https://team-home.netlify.com/

Back end deployment with users displayed:<br/>
https://team-home.herokuapp.com/graphql?query={users{_id%20firstName%20lastName%20email}}

