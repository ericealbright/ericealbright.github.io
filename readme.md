ericealbright.github.io
========

To test locally @ http://localhost:4000
~$bundle exec jekyll serve

To deploy to http://ericealbright.github.io
~$git add --all
~$git commit -m "Initial commit"
~$git push -u origin master

Custom Domains
--------
To setup the DNS info to use a custom domain I followed the tutorial here:
http://www.curtismlarson.com/blog/2015/04/12/github-pages-google-domains/

Some problems I ran into:
--------
To fix kramdown dependency error during a "jekyll build -trace"
~$bundle clean --force

I was also having problems with regeneration of the site after making changes while the jekyll server was running. I was getting this error:

GitHub Metadata: No GitHub API authentication could be found. Some fields may be missing or have incorrect data.

	Error: SSL_connect returned=1 errno=0 state=SSLv3 read server certificate B: certificate verify failed

	Error: Run jekyll build –trace for more information.

I followed the tutorial here:
https://www.hieule.info/programming/fix-errors-github-metadata-ssl-certificate-running-jekyll-serve/

Note that I had to restart my pc to get this fix working with GitBash. It worked right away with the Windows CMD prompt.