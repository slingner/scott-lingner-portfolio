---
# make sure to update this title in the image mapper on ArrowCard if changed
title: "Student portfolios - Prenda"
description: "Created a student portfolio dashboard to showcase work and progress."
date: "2024-08-10"
banner: "/prenda.png"
demoURL: "https://www.prenda.com/"
repoURL: "https://github.com/prenda-school/prendaworld"
---

## 🎓 Prenda

I wanted to start with a little background into Prenda, the ed-tech company I’ve been working for for the last four years. Prenda helps adults create microschools in their homes, usually around 5-10 kids. The whole model behind Prenda is based on mastery-based learning, where kids can learn at their own pace and truly master a subject before moving on. There are four different modes in the Prenda curriculum that kids bounce around throughout their 4-hour school day, each one targeting a different aspect of learning. This approach empowers the students to want to learn.

#### The problem

Students' work had nowhere to live in Prenda. It was scattered between the four different learning modes (Connect, Conquer, Collaborate, Create), making it difficult to share their work with their teachers and parents.

#### The solution

The solution to this was to create a student portfolio that combined all of the modes into one location, where images, notes, and other stats could be stored and shared between students, guides, and parents.

### 🚀 Key features

This dashboard seamlessly integrates with Prenda's various learning tools and includes several key features, such as a project detail page where students can display their work through photos, videos, and written reflections. It also includes a "Favorites" section where students can explore and create a list of their favorite projects, along with filtering options by mode, subject, date, and more.

The tool is accessible not only to students but also to teachers, who can approve or reject portfolio submissions and leave comments, fostering a more interactive and supportive learning environment.

![Student portfolios dashboard](/portfolio.png)
Student portfolios dashboard for students to showcase their work and progress.

![Student portfolios enlarged view](/portfolio-enlarged-view.png)
A project detail page that showcases the student's work, including photos, videos, and written reflections.

### 🛠️ Tech stack

This tool was built using React, with React Router for efficient page navigation, a customized Prenda design system for styling, and AWS for photo storage. Thousands of existing portfolio projects were stored in MongoDB before beginning this project, and we decided to retain the data there while migrating to an updated model to ensure a smooth transition.

## Frontend

On the front end, we use React with Meteor. Meteor was initially chosen back in 2018 when Prenda was starting, and we were starting to see the site slow down due to Meteor’s monolithic structure. The team was considering switching to Next.js in the future, which could handle scaling much better and offer easier integrations to deployment tools like Vercel and for server-side rendering.

For navigation on the front end, I used React Router API. This was useful for having a clear separation between the different views in the app (the teacher and the student).

For managing state throughout the portfolio, we relied on React Context API. This was useful to avoid prop drilling between all of the components. We used three different contexts to handle different aspects of the portfolio.

We also had a custom design system that was designed by our UX team, which used Material UI as the base.

## Backend

The backend for this project, called "Hub," acts as the core API for managing Prenda’s data. It is a Node.js application that integrates with two databases: MongoDB and Postgres.

* MongoDB is used primarily for student-related data due to its flexibility and dynamic schema, which suits the unpredictable and evolving nature of student projects and activities.
* Postgres is utilized for business logic and admin-related operations, such as enrollments, payments, and background checks. Its relational structure and robust querying capabilities make it ideal for these tasks.

For testing, we decided as a team that every new command or query should have an integration test, as well as Cypress end-to-end tests. We also have GitHub actions in place that prevent the PR from merging to develop if any tests break.

## Performance Improvements

One issue we discovered right before releasing this product was related to performance. Initially, we decided to grab the images on the client side, but through testing, we realized this approach was a mistake. It led to performance issues and slow loading times. To resolve this, we rewrote the logic to pull images on the server side and implemented pagination, so that only the first 8 images would show up initially. This change significantly improved the performance and user experience.

Want to read a more detailed account of my work at Prenda? [Check out my post here](/blog/02-working-at-an-education-startup).