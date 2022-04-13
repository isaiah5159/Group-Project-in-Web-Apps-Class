# *DogMe* by Software Benders

*Woof woof!* DogMe is a presentation evaluation app that allows students to give each other feedback with scoring on four categories: organization, visuals, content, and delivery. It also allows instructors to monitor everything that goes on.

Made by Software Benders ([Jay Collins](https://github.com/JTCollins33), [Isaiah Green](https://github.com/isaiah5159), [Ryoma Kawakami](https://github.com/ryomakawakami), [Goodman Li](https://github.com/Gli9249))

[![Rails Style Guide](https://img.shields.io/badge/code_style-rubocop-brightgreen.svg)](https://github.com/rubocop-hq/rubocop-rails)

## Table of Contents
- [Setup](#setup)
- [Usage](#usage)
- [Group Work](#group-work)

## Setup

Download the repository via SSH or HTTPS.

Change to the eval directory
```
cd eval
```
Install required modules with
```
bundle install
yarn install --check-files
```
Then, set up the database by running
```
rails db:migrate
```

Open [config/info.yml](eval/config/info.yml) and add emails for admins, instructors, and students. Only the emails that have been added to this configuration file can be used to sign up. Ensure that there is at least one admin email address.

Run the server with
```
rails s
```
Connect to localhost:3000 and create your admin account, using the email address you added in the configuration file. Note that you will have to restart the server for changes to the configuration file to be reflected. You can stop the server by pressing Ctrl-C in the terminal.

## Usage

There are three types of users with differing permissions, as shown in the following table:

Action | Student | Instructor | Admin
------ | ------- | ---------- | -----
Create and delete a presentation | | ✔️ | ✔️
Give feedback to a presentation | ✔️ | |
Give feedback to each student for a presentation and assign a score | | ✔️ | ✔️
View feedback for own presentation | ✔️ | |
View gradebook | | ✔️ | ✔️
View admin dashboard | | | ✔️
Edit and remove student accounts | | ✔️ | ✔️
Edit and remove instructor accounts | | | ✔️

Once the website is up and running, users will be able to sign up or sign in (if they already have an account active). All you have to do is to add student and instructor emails to [config/info.yml](eval/config/info.yml). You can also change the category_max value to change how many points each category (organization, visuals, content, delivery) is graded out of.

When you log in as an admin, you will be taken to your home page. Here, you will be able to view all of the presentations you have created so far, as well as create new presentations. When creating a new presentation, you must specify a presentation name and select at least one user who will give the presentation. Note that you will need to have the student(s) signed up to the website to select them. Also, you can click on the presentation name to view all of the feedback that students have given the presentation. Finally, you can give each student their individual feedback by clicking on their name in the second column. Their name will be crossed out when their feedback has been written and a score has been assigned.

In the gradebook tab, you will be able to see each student with their average score, final scores, and number of feedbacks they haven't done. You can click on the show button on the right of each student to see all of the feedback they have written. Similarly to this, in the admin tab, you can view a similar table with the instructors. It lists the number of feedbacks that they've given, as well as the average score that they have assigned students. This is useful for monitoring everyone's contributions.

The roster tab lists all of the users for the page. You can modify people's names, as well as delete users from the page.

Instructors have the same privileges as you, except that they cannot see the admin dashboard and they cannot modify or delete instructors in the roster. Students only have one page, where they can give feedback and view instructor and student feedback that they have been given.

## Group Work

Jay Collins - Presentation and feedback forms

Isaiah Green - Login system

Goodman Li - User pages

Ryoma Kawakami - Home page and view for feedback

Everyone - Worked on readme, code style, and overall functionality
