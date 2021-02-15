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
        heroku create myappname

5. Create Procfile in your root 

    touch Procfile

    Inside Procfile add the following:
    web: npm start
    Note: note if you're not using npm, you can try something like 'web: node app.js' instead

6. Push to heroku

    git add --all 

    git commit -m “first commit"

    git push heroku main 
    

7. Spin up a Server. Assign a free server to run the website:

    heroku ps:scale web=1

8. Set up your Production Database. Create a database to host your production data:

    heroku addons:create mongolab:sandbox

8. If you have .env variables. Push them to heroku as well:

    Ex: 

    heroku config:set DATABASE_URI=database_uri_here

9. Open your app. 
    You can open it from dashboard or simply run:

    heroku open 




