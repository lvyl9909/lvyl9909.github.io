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
