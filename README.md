# Sprint Challenge: Authentication - Dad Jokes

## Description

In this challenge, you build a real wise-guy application. _Dad jokes_ are all the rage these days. Currently the application is trying to receive some `Dad Jokes`, however we are locked out.

## Instructions

**Read these instructions carefully. Understand exactly what is expected _before_ starting this Sprint Challenge.**

This is an individual assessment, please work on it alone. It is an opportunity to demonstrate proficiency in the concepts and objectives introduced and practiced in preceding days.

If the instructions are not clear, please seek support from your TL and Instructor on Slack.

The Minimum Viable Product must be completed in three hours.

Follow these steps to set up and work on your project:

- [ ] Create a forked copy of this project.
- [ ] Add your _Team Lead_ as collaborator on Github.
- [ ] Clone your forked version of the Repository.
- [ ] Create a new Branch on the clone: git checkout -b `firstName-lastName`.
- [ ] Implement the project on this Branch, committing changes regularly.
- [ ] Push commits: git push origin `firstName-lastName`.

Follow these steps for completing your project.

- [ ] Submit a Pull-Request to merge `firstName-lastName` branch into `master` on your fork. **Please don't make Pull Requests against Lambda's repository**.
- [ ] Please don't merge your own pull request.
- [ ] Add your _Team Lead_ as a Reviewer on the Pull-request
- [ ] Your _Team Lead_ will count the challenge as done by merging the branch into _master_.

## Commits

Commit your code regularly and use descriptive messages. This helps both you (in case you ever need to return to old code) and your Team Lead.

## Self-Study/Essay Questions

Demonstrate your understanding of this week's concepts by answering the following free-form questions. Edit this document to include your answers after each question. Make sure to leave a blank line above and below your answer so it is clear and easy to read by your project manager.

- [ ] What is the purpose of using _sessions_?

A ‘session’ is used to store information about a client that can be used later so that a user doesn’t need to keep logging in over and over to access different parts of the App.  Depending on a user authorization privileges, they can enter certain places, but perhaps not others.  Session storage can also store many other things beside a password, which can be accessed later if necessary.

- [ ] What does bcrypt do to help us store passwords in a secure manner.

The module import, bcryptjs, is used to hash a password into a long, scrambled list of characters that no longer resemble the original password, which is makes it more difficult to understand what the password and avoids using plain text.

- [ ] What does bcrypt do to slow down attackers?

In order to protect a password, bcrypt will hash the password by salting it and then running the algorithm many times.  Salting is just a way to add extra characters and complex to the original password.  Then adding more algorithm iterations makes it even more complex.  It’s like taking a box of Christmas lights, throwing in extra light bulbs, then shaking up the box several different times.  In the end, they will come out of the box all tangled and twisted together and make no sense.

- [ ] What are the three parts of the JSON Web Token?

A JSON web token will have three parts: 1) header, 2) payload, and 3) signature.  The header specifies which type of algorithm and token type is being used to generate the token.  The payload is just whatever object is being stored on the token, such as the id, username, role, etc.  It’s good to limit this to a small amount of information to help speed up performance.  The signature is the piece that is secret and authenticates that yes, the token is bona fide genuine.  These three pieces of information are put together in one token and separated by a dot period. 

## Minimum Viable Product

Implement an User Authentication System. Hash user's passwords before saving them to the database. Use `JSON Web Tokens` or `Sessions and Cookies` to persist authentication across requests.

- [ ] Implement the `register` and `login` functionality inside `/auth/auth-router.js`. A `user` has `username` and `password`. Both properties are required.
- [ ] Implement the `authenticate` middleware inside `/auth/authenticate-middleware.js`.
- [ ] Write a **minimum o 2 tests** per API endpoint. Write more tests if you have time.

**Note**: the database already has the users table, but if you run into issues, the migrations are available.

## Stretch Problem

Build a front end to show the jokes.

- [ ] Add a React client that connects to the API and has pages for `Sign Up`, `Sign In` and showing a list of `Jokes`.
- [ ] Once you have the functionality down, style it!
