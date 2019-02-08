---
date: "2019-02-07"
title: "Labs Week 5"
category: "Lambda Labs"
---

## Individual Accomplishments

[@zacharyarney](https://github.com/zacharyarney)

[Contribution Graph](https://github.com/Lambda-School-Labs/labs9-team-home/graphs/contributors?from=2019-01-19&to=2019-01-27&type=c 'Github Repository Contribution Graph')

<!-- Provide a paragraph (5-8 sentences) summarizing the work you did this week, the challenges you faced, the tools you used, and your accomplishments. -->
This week we started off with what was supposed to be a finished--or close to finished--product. What we had to start had most of the functionality required to meet MVP but was largely unpolished and suffered from many bugs. This week was mostly about finding and eliminating as many bugs as possible and refining the styling of the app. We faced some challenges getting some of our third-party libraries to play nicely with each other. Material UI and styled-components continued to create problems throughout the week. I also think it's easier to try and fix bugs as early in the process as possible, but with a team of five people and strict weekly deadlines, that isn't always possible. New bugs are created due to the disparate nature of working on a team and aren't always found immediately. It seems like these bugs end up being harder to fix because you are forced to work around the pre-existing codebase. But these challenges just mean more creative coding is required. 

## Tasks Pulled

### Front End

- Adds security notes about FilePond type validation to front end README
  - [Trello link](https://trello.com/c/zgXRYpcd/189-security-readme)
  - [Github link](https://github.com/Lambda-School-Labs/labs9-team-home/pull/189)
- Paywall front-end
  - [Trello link](https://trello.com/c/hSCR6UvV/156-paywall)
  - [Github link](https://github.com/Lambda-School-Labs/labs9-team-home/pull/203)
- Billing page styling (no user feedback yet)
  - [Trello link](https://trello.com/c/aXKFSq0B/3-billing-page)
  - [Github link](https://github.com/Lambda-School-Labs/labs9-team-home/pull/208)
- Billing user feedback
  - [Trello link](https://trello.com/c/aXKFSq0B/3-billing-page)
  - [Github link](https://github.com/Lambda-School-Labs/labs9-team-home/pull/216)
- Billing page styling
  - [Trello link](https://trello.com/c/aXKFSq0B/3-billing-page)
  - [Github link](https://github.com/Lambda-School-Labs/labs9-team-home/pull/218)
- Settings page update
  - [Trello link](https://trello.com/c/zUffKRE4/4-user-settings-page)
  - [Github link](https://github.com/Lambda-School-Labs/labs9-team-home/pull/232)

## Detailed Analysis

<!-- Pick one of your tickets and provide a detailed analysis of the work you did. This should be approximately 1/4 page of text, and at least three screenshots. -->
Something that slipped by us while working on the project was the functionality of our paywall. We had Stripe set up pretty early on to process payments, but we didn't have any limited features in the free version of the app to access through payment. I took on the task this week of implementing the actual paywall. What I had to start with was a billing page that consisted solely of a button to bring up the Stripe modal. Processing a payment would trigger a GraphQL mutation function that switches the premium status on the Team model for a given team from the default `false` to `true`. A teammate did some work on the backend to use this boolean to unlock the ability to invite unlimited people to a team (the free version limits 5 to a team). 

Stripe was initially set up with a hard-coded team ID, so I had to make the team ID passed into the Stripe function dynamic. I did this by setting up a list of teams on the billing page for the user to pick from. The list filters a findTeamByUser query to include only teams for which the user has admin status and maps over those results to create a list of clickable cards. The cards function sort of as radio buttons where selecting a team sets it's ID on state which is then passed down to the Stripe component to be passed into the mutation. The component also checks to see if the ID on state matches it's own team ID and uses that flag to trigger a change in styled-components and highlight the card that is currently selected. So a user clicks on a team and then clicks the `Go Premium` button and premium status will be applied to the selected team.



Event handler to set state to selected team ID<br />
![Event handler to set state to selected team ID](https://www.dropbox.com/s/z9tmxqjrzt9i6y9/Screen%20Shot%202019-02-08%20at%2012.17.36%20AM.png?raw=1 'Event handler to set state to selected team ID')

GraphQL qruery to get all teams where user is admin<br />
![GraphQL qruery to get all teams where user is admin](https://www.dropbox.com/s/95gsd0p2c73he04/Screen%20Shot%202019-02-08%20at%2012.20.44%20AM.png?raw=1 'GraphQL qruery to get all teams where user is admin')

Logic for selection highlighting<br />
![Logic for selection highlighting](https://www.dropbox.com/s/h0j7ixyd18pwb39/Screen%20Shot%202019-02-08%20at%2012.22.03%20AM.png?raw=1 'Logic for selection highlighting')

## Presentation and Making a Finished Product

<!-- Description from labs training kit page for the week -->
My biggest woes by the end of this are with styling. Specifically with the way Material UI plays with styled-components. While there are workarounds in place to allow the two to work together, neither were designed to work with the other and because of this there are many little UI bugs that have proven very difficult to fix. Things like font consistency, form consistency, consistency in general--something that both of these libraries are made to address--became kind of a jumble at the end. Scope seems to behave inconsistently and some global styles will apply to most things but not all things and other inherited styles will only work in some places. This leads to a lot of manual overrides. Another problem I ran into is the relationship between React and Apollo/GraphQL. Apollo has it's own store and caching system built in which can be very useful but also challenging when it comes to getting React to update the virtual DOM when information on the back end is updated. In the end we have an app that mostly works and looks half-decent. Knowing about all of the ugly machinery under the hood makes the app feel less polished than it probably is. Half of the battle is just hiding that ugliness under something shiny.

## Weekly Milestones

https://team-home.netlify.com/

- Consistent styling
- No/minimal bugs
- All features functioning correctly
