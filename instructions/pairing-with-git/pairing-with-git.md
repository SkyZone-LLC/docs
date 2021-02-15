## Pairing with git

## Getting started <!-- {docsify-ignore} -->
You and your partner should follow these instructions together. "PartnerA" will assume the role of "driver" first, and "PartnerB" will assume the role of "navigator" first - decide now who those will be. You should switch these roles every 15 minutes (use a timer to keep track).

The steps below will help you establish a workflow for sharing your work with each other using Git. Note that for this to work, it is very important that only one partner works on the project at a time - you must stick to the driver/navigator roles.

- Both partners should fork the repo and clone their fork to their respective machines.
- **PartnerA**: Copy the url for your fork's github page from your browser's url bar (it will be something like `https://github.com/<PartnerA_username>/<PairExercise>`) and send that url to PartnerB via Slack
- **PartnerB**: Copy the url that PartnerA sent you, `cd` into your local clone on your machine and execute this command using that url:

Note: No need to include the "<" ">" listed below

```bash
git remote add partnerA <partnerA_github_url>
```
- Repeat the two steps above, swapping PartnerA and PartnerB
- Both partners should read the `README.md` of the project (separately)
- Once both partners have read the `README.md`, **start the pairing timer** and complete the workshop steps in order

## When it's time to switch roles <!-- {docsify-ignore} -->
- PartnerA should commit all of their work and push it to their master branch of the project directory:
```bash
git add -A
git commit -m "Meaningul commit message"
git push origin main
```
- PartnerB should then **pull** from **their partner's remote** (NOT from their own origin) in their project directory:
```bash
git pull partnerA main
```
- Once PartnerB completes the pull, they will have all of PartnerB's work, and you will both be ready to continue with roles reversed. When the time comes to switch again, you simply perform the same process (with roles reversed).



<!-- HEROKU NODE APP  -->

# Deploy NODE APP to heroku

- MongoDB for the database
- Node & Express for the server-side

**Client side projects can be deployed in a same way with only expection you don't have to create sandbox for database**


### Prerequisite

1. Make sure you have heroku account open.
If not open here: `www.heroku.com`

2. Make sure heroku-cli is installed. 
If not install cli here `https://devcenter.heroku.com/articles/heroku-cli#download-and-install`

3. Make sure your project is in in git.

To verify run in terminal and in project directory:

`git remote -v` 

This should show something like this:

```
heroku https://git.heroku.com/myappname.git (fetch)
heroku https://git.heroku.com/myappname.git (push)
origin git@github.com:urakymzhan/myappname.git (fetch)
origin git@github.com:urakymzhan/myappname.git (push)
```

or just do `ls -al` and make sure .git file is there

4. Create an application in heroku
    a. Through heroku.com dashboard:
        1. Go to Heroku.com
        2. Click on your "Dashboard"
        3. Click "New"
        4. Click "Create New App"
        - Give the app a name and click "Create App". This name is the default url to this app when you're done (ex: myappname.herokuapp.com)
    b. Through heroku.com dashboard:
        1. `heroku create myappname`

5. Create Procfile in your root 
`touch Procfile`

Inside Procfile add the following:
web: npm start
Note: note if you're not using npm, you can try something like 'web: node app.js' instead

6. Push to heroku
    `
    $ git add . 
    $ git commit -m “first commit”
    $ git push heroku main
    `

7. Spin up a Server. Assign a free server to run the website:
`$ heroku ps:scale web=1`

8. Set up your Production Database. Create a database to host your production data:
`$ heroku addons:create mongolab:sandbox`

8. If you have .env variables. Push them to heroku as well:
Ex: `$ heroku config:set DATABASE_URI=database_uri_here`

9. Open your app. 
You can open it from dashboard or simply run:
`$ heroku open `