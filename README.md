# Co-op prototyping kit

[![Heroku](https://heroku-badge.herokuapp.com/?app=eleventy-prototyping-kit)](https://eleventy-prototyping-kit.herokuapp.com/)

A project scaffold that can be used for prototypes that can be deployed to Heroku for user research. This is not intended to be used for production websites.

This project is based on the [Eleventyone starter created by Phil Hawksworth](https://github.com/philhawksworth/eleventyone).

[Eleventy](https://11ty.io) is very similar to jekyll the static site generator used in the old prototyping kit - however we're hoping this is far simpler to set up and use.

Included:

- [Eleventy](https://11ty.io) with a skeleton site
- A CSS pipeline with PostCSS
- An inline JS pipeline
- The Co-op foundations, elements and components ready to use
- [Browsersync](https://browsersync.io/) for testing
- Instructions on how to deploy to Heroku


## Instructions

### Getting started
To get a copy ready to work with:
- use the 'code' button on this page and select 'download zip'
- upack the folder and rename it 
- move the folder to where you keep websites

### Prerequisites
You'll need [Node.js](https://nodejs.org/) and [NPM](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm) installed. When you run the next step these will be installed autoamtically, however on Co-op Macs you may not have permissions to do this. 

If you get an error:

1. Log out.
2. Log back in as the admin account.
3. Choose Apple menu > System Preferences.
4. Click Users & Groups.
5. Click the lock icon to unlock it, then enter an administrator name and password.
6. Select a standard user or managed user in the list of users, then select “Allow user to administer this computer.”
7. Log out of the admin account.
8. Log back in with your standard account.

### Running locally
In a terminal window navigate to the website folder. If you don't know how to do this open terminal and drag the folder into it. That will put terminal into the right place. Once there type:

```bash
# install the dependencies
npm install
```
And press enter. Then type:

```bash
# The site will then run locally
npm start
```
And press enter.

You should see the following URLs in your terminal window where you can access your website and the Browsersync dashboard:

```bash
[Browsersync] Access URLs:
 -------------------------------------
       Local: http://localhost:8080
    External: http://192.168.0.13:8080
 -------------------------------------
          UI: http://localhost:3001
 UI External: http://localhost:3001
 -------------------------------------
[Browsersync] Serving files from: dist
```

### Deploying to Heroku

If you want to publish your prototype to Heroku, a few more steps are necessary:

#### 1. Create the prototype repository

Create a new repository for your prototype on Github (make sure the new repository is set to private if necessary).

Link your local copy to the newly created Github repository. Make sure that you change your-repository-name to the name of the repository which you made above:
```sh
cd your-prototype
git init
git commit -a -m "Initial commit"
git remote add origin git@github.com:coopdigital/your-repository-name.git
git push -u origin master
```

#### 2. Create the prototype app on Heroku
The next step is to create a new app within the Co-op's enterprise Heroku account. 

#### 3. Configure buildpacks
Once you have your app, in the Settings tab, add the NodeJS the and static buildpacks:
- `heroku/nodejs`
- `https://buildpack-registry.s3.amazonaws.com/buildpacks/heroku-community/static.tgz`


#### 4. Deploy your website
In the deploy tab:
- choose 'Connect to Github' as the deployment method
- search for and connect to the repository you have created
- enable 'Automatic Deploys for this app' or use the deploy from branch option to deploy maunally from the main branch

You will then see your website at [website-name].herokuapp.com

You can test that your app is building and deploying correctly by running a manual deployment from the Deploy tab. If you have enabled automatic deploys, the app will automatically rebuild and deploy when changes are pushed to the master branch.