---
layout: post
title:  Exercise At Home
date:   2017-10-07
img: ic_exerciseathome.png
description: Exercise At Home is an Android app designed to give patients who need physical therapy the motivation they need to stick with their regimen.
categories: projects
---

Exercise At Home is an Android app designed to motivate patients who need physics therapy.

To accomplish this, Exercise At Home employs stat tracking and gamification elements. Exercises are performed live in-app, with the help of **voice narration** and **range-of-motion** measurements acquired through various sensor fusion algorithms.

<img style="float: left; width: 30%; margin-right: 1em;" src="https://lh3.googleusercontent.com/oNxWjxefGsvomuKdO3GvCCAJp4YBwRwVIo8XVfjZ0sO6EOYouH38gOccNV52TyRhwjs_=h900-rw" />

## Background

Our client, an Orthopedic Surgeon at a local VA Clinic, made it clear to us that a lot of patients who undergo surgery _don't_ perform physical therapy exercises designed to help with their treatment. Patients either don't feel the exercises work, or are just too lazy to perform them. Some even lie to their therapist out of guilt, which doesn't end up helping anyone. Our client felt that all the patients needed was some push to help them form a habit around their physical therapy.

We brainstormed and came up with a couple potential solutions. Patients saw the exercises as tedious and not worth their time doing, so gamifying the exercise process has a huge potential to help convince patients to perform them anyway. We also wanted tie those game elements with actual exercise statistics, similar to existing exercise apps, for those interested in their progress over time.

## What it does

There are two components to Exercise At Home.

#### Web
The website, hosted at [exerciseathome.co](https://www.exerciseathome.co) (site went down :cry:) acts as both an admin portal designed for therapists to view patient progress, and a domain for our REST endpoints that the mobile app can access.

#### Mobile
The mobile app is an Android client for patients that provides useful stat tracking and digital incentives to exercise. Each time a patient exercises with the app, they'll get points they can spend, and experience to level them up. Consistently exercising awards streaks that increase the amount of points they end up getting. We also award badges after certain events (Complete your first exercise, Get a 3-exercise streak, etc.) to  act as a patient's achievements. Points are spent on themes, which allow patients to reskin most of the app to their liking.

Patients can schedule certain exercises to perform weekly on whatever days they need, and optionally get notifications reminding them about it. Stats showing miscellaneous stats, like max angle, average angle, and duration show for each exercise, letting patients know their progress over time.

## Development
Exercise At Home was developed as part of UCF's Senior Design program in a team of four.

We self-assigned two people to work on the web backend, and two people, including me, to work on the Android app. The backend was completed first, so eventually it did turn into all four of us working on the Android app. We split up all of our work into logical segments, ensuring we never stepped on each other's toes _too_ much and conflicts, if they did arise, would be solved through Git.
<img style="float: right; width: 30%; margin-left: 1em; margin-top: 1em" src="https://lh3.googleusercontent.com/c9uKn36dXnUX-Hd1QKQn1Jb_oa3N3CjDb5U2uBzQYhfhlKnpXVPm4GzXxFAg4MvqOg=h900-rw" />
I gradually took charge of design for both the presentation layer and parts of the UI itself, and influenced much of the business logic present.

The app follows an MVP architecture with various interactors and repositories to fulfill use cases. We also employ drop-in strategies for the sensor measurements utilizing different combinations of sensors to help work around certain phones with absent or wonky accelerometers or gyroscopes.

## Retrospective
 This was the first _real_ Android app I've worked on, and around the same time I was reading into [architectural](https://en.wikipedia.org/wiki/Architectural_pattern) [design](https://8thlight.com/blog/uncle-bob/2012/08/13/the-clean-architecture.html) [patterns](https://en.wikipedia.org/wiki/Software_design_pattern) on [Android](https://fernandocejas.com/2014/09/03/architecting-android-the-clean-way/). So I was very interested in applying these concepts here, if anything because our client was interested in continuing this project with a second Senior Design group after we were done and I wanted to "keep the room clean" for them.

 Then came justifying some of these decisions to the other team members. A few had pretty obvious benefits, like using a [strategy pattern](https://en.wikipedia.org/wiki/Strategy_pattern) to hotswap different sensor strategies depending on a phone's capabilities. Other things, like [Model-View-Presenter (MVP)](https://antonioleiva.com/mvp-android/), I don't think I was able to explain as well at the time. One of the biggest issues I ran into with trying to decipher MVP was how many slight variations there were. It seemed like there was no canonical version of it to learn first. Granted that proved to be a huge benefit, as we were able to tailor our usage of MVP to our own skill level. Finding the right balance between trying out new technologies vs the familiarity needed to get things done is probably my biggest takeaway from this project.
