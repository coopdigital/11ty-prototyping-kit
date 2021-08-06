# Co-op prototyping kit

[![Heroku](https://heroku-badge.herokuapp.com/?app=eleventy-prototyping-kit)](https://eleventy-prototyping-kit.herokuapp.com/)

A project scaffold that can be used for prototypes that can be deployed to Heroku for user research.

This is a WIP project based on the [Eleventyone starter created by Phil Hawksworth](https://github.com/philhawksworth/eleventyone).

Included:

- [Eleventy](https://11ty.io) with a skeleton site
- A CSS pipeline with PostCSS
- An inline JS pipeline
- The Co-op foundations, elements and components ready to use
- Instructions on how to deploy to Heroku


## Instructions

## Prerequisites

- [Node and NPM](https://nodejs.org/)

## Running locally

```bash
# install the dependencies
npm install

# The site will then be available locally
npm start
```

## Deploying to Heroku

If you want to publish your prototype to Heroku, a few more steps are necessary:

## 1. Create the prototype repository

Create a new repository for your prototype on Github (make sure the new repository is set to _Private_ if necessary).

Link your local copy to the newly created Github repository. Make sure that you change your-repository-name to the name of the repository which you made above:
```sh
cd your-prototype
git init
git commit -a -m "Initial commit"
git remote add origin git@github.com:coopdigital/your-repository-name.git
git push -u origin master
```

## 2. Create the prototype app on Heroku
The next step is to create a new app within the Co-op's enterprise Heroku account. 

## 3. Configure buildpacks
Once you have your app, in the Settings tab, add the _NodeJS_ the and _static_  buildpacks:
- `heroku/nodejs`
- `https://buildpack-registry.s3.amazonaws.com/buildpacks/heroku-community/static.tgz`


## 4. Deploy your website
In the deploy tab:
- choose 'Connect to Github' as the deployment method
- search for and connect to the repository you have created
- enable 'Automatic Deploys for this app' or use the deploy from branch option to deploy maunally from the main branch

You will then see your website at [website-name].herokuapp.com

You can test that your app is building and deploying correctly by running a manual deployment from the Deploy tab. If you have enabled automatic deploys, the app will automatically rebuild and deploy when changes are pushed to the master branch.