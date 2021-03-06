# Final Project

FOCUS: UX Design

Created New project branch: UX Design

Project is the design of a website for questions and answer, very similar to something like reddit
You register on the site and then have the ability to post a question that can then be answered. 

_Moved answerform to the questions page_

My final project's original design can be seen here - 

https://github.com/on28/MiniProject3/blob/master/Before.png

https://github.com/on28/MiniProject3/blob/master/before2.png

Questions were asked on one page of the site and then the user had to be taken to another page in other to answer the question
With the way that the web is used today, this does not suffice and we needed another way to integrate the answerform
into same page as the question that a user asks. 

This would eliminate the need for each user to go to a different page to answer and read prior answers each time

This change still reserves the user's ability to view an answer in a case where the response is too long in a different page

Old answer page - 
https://github.com/on28/MiniProject3/blob/master/before3.png

With code changes, labels and other design,

The new question and answer page now looks like this - 

https://github.com/on28/MiniProject3/blob/master/New.png

A user can now easily read all previous answers without going from page to page and also provide their own answers all
from same page.

# Testing

To test the functionality of this site, I used laravel dusk

I have created two tests, one to check and make sure that a person can register sucessfully and another to check and 
make sure that a person can login

***The register test may need to be edited with a new email address to allow for the new user to be created

# login test

        $this->browse(function (Browser $browser) {
            $browser->visit('http://localhost:8000/')
                ->clickLink('Login')
                ->assertSee('Login')

                ->value('#email', 'test22@test.com')
                ->value('#password', 'test123')
                ->click('button[type="submit"]')
                ->assertPathis('/home')
                ->assertSee("Questions");

# Register Test

    this->browse(function (Browser $browser) {
                $browser->visit('http://localhost:8000/')
                    ->clickLink('Register')
                    ->assertSee('Register')
                    
                    ->value('#email', 'test350@test.com')
                    ->value('#password', 'test123')
                    ->value('#password-confirm', 'test123')
                    ->click('button[type="submit"]')
                    ->assertPathis('/home')
                    ->assertSee("Questions");

# MiniProject3
FAQ project to build a question and answer forum using laravel.
In this mini project we setup the database models, migrations, unit tests, and seeds for the FAQ project's users, profile,
questions, and answers. You must make a new branch for each feature and commit each feature to that branch as it's completed.
Each branch (Profile, Question, Answer) should have the model, migration, factory, test, and seed files for it. You need to submit a github repo, a screenshot(s) of your tests, and a link to the project working on heroku. 
