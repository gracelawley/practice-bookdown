  [![Travis build status](https://travis-ci.org/gracelawley/practice-bookdown.svg?branch=master)](https://travis-ci.org/gracelawley/practice-bookdown) [![Netlify Status](https://api.netlify.com/api/v1/badges/2f326b36-6ea6-465e-ab15-66ebdd84a3ec/deploy-status)](https://app.netlify.com/sites/zen-northcutt-9b57e6/deploys)

# How to use Netlify's [redirect & rewrite rules](https://www.netlify.com/docs/redirects/) in a Bookdown + Travis-CI + Netlify workflow

1. Add a `_redirects` file to the root of the project. Follow [Netlify's documentation](https://www.netlify.com/docs/redirects/) to configure the redirect & rewrite rules that you want to add.
1. Add `script: cat _redirects >> _book/_redirects` to `.travis.yml`. 
  + This will copy the contents of `_redirects` and save it as a new file: `_book/_redirects`.
  + This is needed because Netlify will look for the `_redirects` file in whatever directory you are telling it to deploy, which is `_book` in this case. So we need to tell to Travis to copy the `_redirects` file over when it is building `_book`. 


