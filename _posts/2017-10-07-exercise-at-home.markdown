---
layout: post
title:  Exercise At Home
date:   2017-10-07
img: ic_exerciseathome.png
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes.
categories: projects
---

Exercise At Home is an Android app designed to give patients who need physical
therapy...

:open_hands: **motivation** :open_hands:


To accomplish this, Exercise At Home employs stat tracking and gamification elements. Exercises are performed live in-app, with the help of :loud_sound: **voice narration** :loud_sound: and :ok_woman: **range-of-motion** :ok_woman: measurements acquired through various sensor fusion algorithms.

<img style="float: left; width: 30%; margin-right: 1em;" src="https://lh3.googleusercontent.com/oNxWjxefGsvomuKdO3GvCCAJp4YBwRwVIo8XVfjZ0sO6EOYouH38gOccNV52TyRhwjs_=h900-rw" />

## Background

Our client, an Orthopedic Surgeon at a local VA Clinic, made it clear to us that a lot of patients who undergo surgery _don't_ perform physical therapy exercises designed to help with their treatment. Patients either don't feel the exercises work, or are just too lazy to perform them. Some even lie to their therapist out of guilt, which doesn't end up helping anyone. Our client felt that all the patients needed was some push to help them form a habit around their physical therapy.

We brainstormed and came up with a couple potential solutions. Patients saw the exercises as tedious and not worth their time doing, so gamifying the exercise process has a huge potential to help convince patients to perform them anyway. We also wanted tie those game elements with actual exercise statistics, similar to existing exercise apps, for those interested in their progress over time.

## What it does

There are two components to Exercise At Home.

#### Web
The website, hosted at [exerciseathome.co](https://www.exerciseathome.co) (or it would be if the site was still up :cry:) acts as both an admin portal designed for therapists to view patient progress, and a domain for our REST endpoints that the mobile app can access.

#### Mobile
The mobile app is an Android client for patients that provides useful stat tracking and digital incentives to exercise. Each time a patient exercises with the app, they'll get points they can spend, and experience to level them up. Consistently exercising awards streaks that increase the amount of points they end up getting. We also award badges after certain events (Complete your first exercise, Get a 3-exercise streak, etc.) to  act as a patient's achievements. Points are spent on themes, which allow patients to reskin most of the app to their liking.

Patients can schedule certain exercises to perform weekly on whatever days they need, and optionally get notifications reminding them about it. Stats showing miscellaneous stats, like max angle, average angle, and duration show for each exercise, letting patients know their progress over time.

## Development
Exercise At Home was developed as part of UCF's Senior Design program in a team of four.

We self-assigned two people to work on the web backend, and two people, including me, to work on the Android app. The backend was completed first, so eventually it did turn into all four of us working on the Android app. We split up all of our work into logical segments, ensuring we never stepped on each other's toes _too_ much and conflicts, if they did arise, would be solved through Git.
<img style="float: right; width: 30%; margin-left: 1em; margin-top: 1em" src="https://lh3.googleusercontent.com/c9uKn36dXnUX-Hd1QKQn1Jb_oa3N3CjDb5U2uBzQYhfhlKnpXVPm4GzXxFAg4MvqOg=h900-rw" />
I gradually took charge of design for both the presentation layer and parts of the UI itself, and influenced much of the business logic present.

The app follows an MVP architecture with various interactors and repositories to fulfill use cases. We also employ drop-in strategies for the sensor measurements utilizing different combinations of sensors to help work around <sup><sub><sub>Samsung</sub></sub></sup> phones with absent or wonky accelerometers or gyroscopes.

## Retrospective
 This was the first _real_ Android app I've worked on, and around the same time I was reading into [architectural](https://en.wikipedia.org/wiki/Architectural_pattern) [design](https://8thlight.com/blog/uncle-bob/2012/08/13/the-clean-architecture.html) [patterns](https://en.wikipedia.org/wiki/Software_design_pattern) on [Android](https://fernandocejas.com/2014/09/03/architecting-android-the-clean-way/).
