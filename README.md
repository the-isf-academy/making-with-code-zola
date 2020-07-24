# Making With Code

TODO project overview

## Develop
To develop, start by cloning the repo, installing Hugo (the static site builder we're using for this project), and running a server to host a local version of the site:

    git clone https://github.com/cproctor/making-with-code.git --recurse-submodules 
    brew install hugo
    cd making-with-code/site
    hugo server
    open http://localhost:1313
    
All additions to the website should be developed on a feature branch before they are merged to the master branch (anything in the master branch will be live on the website!). To make a new branch:

    git checkout -b branch-name
    
The Hugo will automatically build the local version as you make changes in the branch. If you ever want to go back to see what's live on the web, you can change back to the master branch:

    git checkout master
    
Don't forget to add/commit/save your work as you go:

    git add file_you_changed
    git commit
    git push

## Deploy
Once you're ready to deploy a change to the website, all you need to do is merge the branch containing your change into the master branch:

    git checkout master
    git merge your-change-branch-name
    **resolve merge conflicts if they occur and commit your manually merged files**
    git push

Github will take it from there! With a baked in action, Github will make a publishable version of the site, put it in a special branch called `gh-pages` and publish the site.
