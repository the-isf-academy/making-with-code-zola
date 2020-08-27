# Making With Code

TODO project overview

## Install
1. Clone the making-with-code repository with it's submodules:

        git clone --recurse-submodules https://github.com/cproctor/making-with-code.git
    
1. Install hugo:

        brew install hugo

## Develop
To develop, start by cloning the repo, installing Hugo (the static site builder we're using for this project), and running a server to host a local version of the site:

    git clone https://github.com/cproctor/making-with-code.git --recurse-submodules 
    brew install hugo
    cd making-with-code/site
    hugo server
    open http://localhost:1313
    
All additions to the website should be developed on a feature branch before they are merged to the master branch (anything in the master branch will be live on the website!). To make a new branch:

    git checkout -b branch-name
    
The Hugo will automatically build the local version as you make changes in the branch. If you ever want to go back to see what's live on the web, you can change back to the production branch:

    git checkout production
    
Don't forget to add/commit/save your work as you go:

    git add file_you_changed
    git commit
    git push

## Deploy
Once you're ready to deploy a change to the website, merge your work branch into
`dev`:

    git merge dev
    git checkout dev
    git merge my-branch
 
Rebuild the site and make sure everything looks ok. Now you're ready to merge
`dev` into `production`. 

    git checkout production
    git merge dev

The production branch is automatically deployed to `cs.fablearn.org`. Github is
set up to invoke a webhook at http://unfold.studio:9000, which is being served
by [webhook](https://github.com/adnanh/webhook). When this URL is requested, a
script is invoked which:

- pulls the latest production branch
- builds the site using the `production` environment
- pushes the built site to `cs.fablearn.org`
