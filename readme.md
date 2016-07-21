ericealbright.github.io
========

To test locally @ http://localhost:4000
~$bundle exec jekyll serve

To deploy to http://ericealbright.github.io
~$git add --all
~$git commit -m "Initial commit"
~$git push -u origin master

Some problems I ran into:
--------
To fix kramdown dependency error during a "jekyll build -trace"
~$bundle clean --force