# DAT250: Software Technology Experiment Assignment 1

### Technical problems that you encountered during installation of the software development environment and how you have solved them

No technical problems that I encountered during installation of the software development environment.

### How you have validated (checked) that the software development environment is working

Checked which version was up and working, and also trying to do some commands and check that they all work as they should.

### Technical problems encountered with the Heroku platform and how you solved them

Problems with port 5000 that was already in use when trying to run the app locally with `heroku local`. Solved by restarting laptop and trying to run again.

### Any pending issues with this assignment which you did not manage to solve

Not really an issue, but just wanted to mention that when writing `heroku addons:create papertrail` it wants me to enter my credit card for billings, which I did not enter. Therefore `heroku addons:open papertrail` could not find any add-ons. However I can see from the tutorial what it is supposed to look like and what information we will get. And then also I do not have the Postgres installed locally, thus could not use `heroku pg:psql` command. I did not know if it was necessary to have it locally, so if it is please do tell and I will install it.
