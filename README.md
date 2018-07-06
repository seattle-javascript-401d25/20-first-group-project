![cf](https://i.imgur.com/7v5ASc8.png) Lab 20: Project Week Kickoff - Group Deployment of Basic Authentication 
======

### The deadline for FULL POINTS for this assignment is *Friday, June 6 by 11:59 p.m*. There will be NO grace period offered on this assignment. Any submissions past this deadline will be docked 2 late points. 

## Instructions

You will be working together to write and deploy a **fully tested basic authentication router** to kick off your project. This will be the first code you commit to your project so you can hit the ground running on Monday without worrying about authentication. 

In other words, everything we did this past Monday for Lab 16 - you're going to do it all over again as a group. 

## Group Workflow Requirements

Please assess your individual abilities and **be honest with yourself and your group members about your skill level**. It's OK to admit you don't understand some of the material, *and* it's OK to be up front that you are technically strong. 

This lab assignment **requires extensive pair programming**. Here is how that works:
  * **People who are not technically strong:** *You should be the driver*. Be sure to listen to your colleagues carefully as they instruct you what you should type, but be sure to ask any clarifying questions about things you don't understand so you can learn from your peers. **You should be the one touching a keyboard most of the time**. Stand up for yourself and do not allow yourself to get steamrolled. 
  * **People who ARE technically strong**: *You should be the navigator*. Your goal is to take on a mentoring role. You already have the technical chops, now you have to refine it with building strong leadership skills that can propel you to senior roles in the industry. Guide your partner through writing the code. Explain what the code does as they type along and answer any questions they have. Use this experience to solidify your own knowledge, and possibly fill in gaps as well as you are forced to explain concepts to someone who doesn't understand them. **Try not to write any code during this time**. Your job is to guide and teach someone else how to write this code.  
  * **If you conclude you are of equal skill level**: Still pair program anyway, but trade off accordingly and explain in your Canvas submission why you felt there was no need to strictly follow the above guidelines

  ### Groups of Three
  * Two people should pair program according to the above guidelines. The third person is allowed to start working on the [project prep requirements due Sunday](https://github.com/codefellows/seattle-javascript-401d25/blob/master/PROJECT.md). You should trade off pair programming accordingly. 
  * For example, Person A and Person B pair program while Person C works on prep materials. After some time, Person B trades places with Person C. Person A and C should decide who should be driving/navigating per the guidelines, and Person B can resume Person C's work on the prep materials. 
  * The third person who is not pair programming is **not allowed** to work on any part of the Basic Authenication code by themselves.
  * *Everyone* should be involved in pair programming at any one point. The odd person out *should not* focus their entire time on the other prep materials while the other two pair program. There should be appropriate trading off. 
  * If you want to mob program as a a group of three, that's OK too. Please decide who should be the driver (**the person who feels not as technically strong as the other two should be doing it**), and explain in your Canvas submission that you mob programmed together. 

  ### Group of Four
  * You should have two pairs. Divide up work evenly between your pairs. For example, Pair 1 can work on writing tests and Pair 2 can work on writing routes. 
  * Please decide who will drive/navigate in your pairs per the above guidelines. 
  * If any one pair finishes their share of work, they are allowed to start working on [project prep requirements due Sunday](https://github.com/codefellows/seattle-javascript-401d25/blob/master/PROJECT.md). Though please assist your colleagues first if they are struggling. 
  * Please trade off partners accordingly if you feel a need to do so.
  
  Please decide candidly who should be driving/navigating. If you conclude you are of equal skill level, then you may trade off evenly with your pair programming. 

  ## Lab Requirements
  * You must create an Account model that that has required `username, email, passwordHash, and tokenSeed` properties.
  * You must implement an `/api/signup` and an `/api/login` route. 
  * You must write basic authentication middleware that authenticates a user who logs into your app. 

 ## Test Requirements
 * **All your tests and your mocks should be written with `async/await`**. 
 * `/api/signup`
    * 200 for a successful response
    * 400 for a bad request
      * You should have **2** test assertions for this status code, one for no username and one for no email
    * 409 for conflicting username/passowrd
      * You should have **2** test assertions for this status code, one for duplicate username and one for duplicate email
      * Day 16 lecture code was not properly setup to allow a 409 error test to pass. Please reference [Day 17 lecture code](https://github.com/codefellows/seattle-javascript-401d25/blob/master/back-end/17-bearer-authorization/basic-bearer-auth/src/router/auth-router.js) instead.
    * 500 (or you can customize the error code)
      * Lack of a password skips to a 500 error in lecture code because that is Bcrypt erring out. You may change this 500 status code to something else, or just test for a 500 in the case of no password provided.
* `/api/login`
    * 200 for a successful response
    * 400 for a bad request 
      * You should have **2** test assertions for this status code, one for no username and one for no password
    * 401 unauthorized for a bad password (**OR** this can be a third 400 test if you would rather make a bad password be a 400 status code)
    * Remember that you will need to **mock a user first before you make a `login` request**



## Github Repo Requirements
* Your team should already have a Github repo by now. Please perform the following steps:
  * Go to your repo's `Settings` 
  * Select `Branches` on the right hand menu
  * Go down to `Branch protection rules` and select `master` from the `Choose a branch` dropdown menu
  * Check `Protect this branch`. 
    * Then check `Require pull request reviews before merging` and `Require status checks before merging` per the image below. Allow any default checked subsettings to stay checked. 

  ![](https://github.com/seattle-javascript-401d25/20-first-project-push/blob/master/branch-protection.PNG?raw=truehttps://github.com/seattle-javascript-401d25/20-first-project-push/blob/master/branch-protection.PNG)


* This makes it so that one teammate must always approve another teammate's PR before merging.

## Continuous Deployment/Continous Integration Requirements
* You should set up Travis CI on your repo and set up continuous deployment with Heroku. 

## Submission Instructions

* Submit on Canvas the following:
  * a link to your `Insights` information on your Github repo that shows the commits of your contributors. You can find this by clicking the `Insights` tab of your repo, and clicking `Contributors`, i.e. [this.](https://github.com/spinaltaper/phrasecraze/graphs/contributors)
  * a link to your PR, or to multiple PRs if you made more than one
  * a link to your deployed Heroku URL
  * a **candid and honest** reflection of how your pair programming/mob programming experience went. 
  * 0's will be given for failing PR's or no Heroku URL. 
  * Personal discussions will be had if the Github insights and/or Canvas reflections indicate the pair programming guidelines were not followed. 


