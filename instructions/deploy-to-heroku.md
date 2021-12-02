## Deploy NODE APP to heroku <!-- {docsify-ignore} -->

- MongoDB for the database
- Node & Express for the server-side

**Client side projects can be deployed in a same way with only expection you don't have to create sandbox for database**


## Prerequisite

1. Make sure you have heroku account open.
    If not open here: `www.heroku.com`

2. Make sure heroku-cli is installed. 
    If not install cli here 
    `https://devcenter.heroku.com/articles/heroku-cli#download-and-install`

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

## Steps

4. Create an application in heroku

    a. Through heroku.com dashboard:
        1. Go to Heroku.com
        2. Click on your "Dashboard"
        3. Click "New"
        4. Click "Create New App"
        - Give the app a name and click "Create App". This name is the default url to this app when you're done (ex: myappname.herokuapp.com)

    b. Through terminal (cmd):
        `heroku create myappname`

5. Create Procfile in your root 

    `touch Procfile`

    Inside Procfile add the following:
    web: npm start
    Note: note if you're not using npm, you can try something like 'web: node app.js' instead

6. Push to heroku

    `git add --all` 

    `git commit -m “first commit"`

    `git push heroku main`
    

7. Spin up a Server. Assign a free server to run the website:

    `heroku ps:scale web=1`

8. Set up your Production Database. Create a database to host your production data:

    **IMPORTANT START**
    If you are using MongoDB Atlas (cloud) Database. Skip this step (8). And simply set you keys to heroku. Either using 9. step or from Heroku Dashboard.

    [Heroku config varts](../_media/heroku_config_vars.png)

    **IMPORTANT END**

    `heroku addons:create mongolab:sandbox`

8. If you have .env variables. Push them to heroku as well:

    Ex: 

    `heroku config:set DATABASE_URI=database_uri_here`

9. Open your app. 
    You can open it from dashboard or simply run:

    `heroku open`



---

# EXTRA

---

## Protecting API Keys in Node

Often times when working with paid APIs, APIs with request limits, or APIs with access to personal account information, such as the Spotify API, we may want to avoid committing our API credentials to Github for the world to see.

Luckily, there is a way to set these values locally without having share them publicly once we push our app up to Github. To accomplish this we'll use what are known as environment variables.

When working on the front-end, we have access to a few global objects such as window, or document, or console which are always available. In Node, we have some other global objects, one of which is process. The process object is automatically available anywhere in Node and contains information about the currently running Node application.

Built into the process object is another nested object: process.env. We can use the process.env object to store and read our environment variables — e.g. values that are specific to the environment or computer where the Node process is running. We'll use these environment variables to store and read our sensitive information.
Safely Setting Environment Variables
In order to safely set environment variables in a Node project, we must first install the dotenv package to our project as a dependency.

```npm install dotenv```

Next, at the entry point for our Node application (the file we run to start our Node app) add the following:

// Read and set environment variables

```require("dotenv").config();```

This code reads any environment variables we assign locally and sets them to the process.env object.
Next, we must create a new file named `.env` at the root of our project. We will use this file to assign our local environment variables. Consider the example .env file:

## Spotify API keys

SPOTIFY_ID=34e84d93de6a4650815e5420e0
SPOTIFY_SECRET=5162cd8b5cf940f48702df

As long as we ran the code in step 2, we'd be able to access these values anywhere in our Node app using the process.env object. 

Example:
// prints `34e84d93de6a4650815e5420e0` to the console
`console.log(process.env.SPOTIFY_ID)`

// prints `5162cd8b5cf940f48702df` to the console

`console.log(process.env.SPOTIFY_SECRET)`

// etc.

Finally, in order to prevent the environment variables we set in the .env file from being pushed up to Github, we must create a `.gitignore` file and add the `.env` file to the list of files to be ignored by git. 

Example:

`node_modules
.DS_Store
.env`


If completed correctly, we should be able to access to any environment variables set in the .env file without having to expose them publicly!

#### Setting Environment Variables on Heroku

If we followed all of the above steps and were to deploy our Node app to Heroku, the deployed application wouldn't have access to the environment variables we set in the .env file as it's being ignored by git. 

Fortunately, Heroku has a means for securely setting environment variables in our deployed apps.
Once your Heroku application has been created, log into your Heroku dashboard at https://dashboard.heroku.com/apps and select your app.

On the following screen, go to the "Settings" tab and click to "Reveal Config Vars".

Heroku Settings

Then add any environment variables being used and their values here.

Heroku Config Vars

Or push variables from terminal as we mentioned in above steps.

If completed correctly, and the API keys set on Heroku correspond to those in the .env file, your application should work the same locally as it does when it's deployed.




