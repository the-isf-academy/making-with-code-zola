# Making With Code

TODO project overview

## Develop

    git clone https://github.com/cproctor/making-with-code.git --recurse-submodules 
    brew install hugo
    cd making-with-code/site
    hugo server
    open http://localhost:1313

## Deploy

Currently, the site is delpoyed by building locally and checking the
built site into source (root dir `/docs`), where GitHub pages automatically
picks it up. It isn't ideal to have the built site in source, but it's not a
huge deal. Maybe someone wants to wire up [this github
action](https://github.com/marketplace/actions/hugo-to-gh-pages)...

    hugo --environment github
    git add ../docs
    git commit -m "..."
    git push
