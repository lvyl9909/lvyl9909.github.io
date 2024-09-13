Prerequisites (Ruby + Bundle)
-----------------------------
1. Download and install a Ruby+Devkit version
NOTE 20240912: GitHub pages now supports Ruby 3.3.4, but still limits support to
jekyll packages including jekyll-scholar

2. Navigate to this folder. Install bundler and gem

NOTE 20240220: Run `gem uninstall -aIx` to uninstall all gems without prompt.
This is useful for a fresh start over.

`bundle install`

3. Test installation status by checking jekyll version 
`jekyll -v`

Test site locally
-----------------
`bundle exec jekyll serve --livereload`

Build site locally
------------------
`bundle exec jekyll build`

Deployment to GitHub Pages
--------------------------

This is currently done by setting up two remote branches: source and gh-pages.

In GitHub repo settings, option "Deploy from a branch" is used on branch
gh-pages, such that any update to the branch will trigger a deployment of the
site.

To ensure a clean gh-pages being maintained, a GitHub automation workflow is set
up in the source branch to automatically copy and paste any published documents
under folder `_site` and overwrite existing files in the gh-pages. This, as
mentioned above, will trigger the actual deployment.

NOTE 20240913: this is a workaround. There should be a neater way by just using
one branch + one automation.
