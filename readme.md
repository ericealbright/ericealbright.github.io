ericealbright.github.io
========

Here's my first try at building a website through GitHub pages using Jekyll. Below you'll find some quick notes on how I run the site, and some notes on problems I ran into.


Using the site
--------
To test locally @ http://localhost:4000

	~$bundle exec jekyll serve

Draft pages are marked with 'draft: true' and drafts are stored in the _drafts folder. To view these during dev use the '--drafts' switch, e.g.:

	~$bundle exec jekyll serve --drafts

To deploy to http://ericealbright.github.io

	~$git add --all
	~$git commit -m "Initial commit"
	~$git push -u origin master

Custom Domain
--------
To setup the DNS info to use a custom domain I followed the tutorial here:
http://www.curtismlarson.com/blog/2015/04/12/github-pages-google-domains/

Custom CSS with SASS
--------
So Jekyll supports SASS but ships with a paired down set of CSS for mark up. I wanted to use Bootstrap, so I followed the tutorial below to get Bootstrap and Font-Awesome set up.

https://dalanzg.github.io/jekyll/2016/03/25/how-to-use-sass-with-jekyll/

_NB_: One gotcha here is that jquery is not included with Bootstrap. So that needs to be added separately. I added the following to my '<head>':



Some problems I ran into
--------
I was getting a kramdown dependency error during a 'jekyll build -trace' that looked something like

	You are missing a library required for Markdown. Please run:
	$ [sudo] gem install kramdown
	Conversion error: Jekyll::Converters::Markdown encountered an error while converting '_posts/2013-08-15-immunize-canada-app.md/#excerpt':
	                Missing dependency: kramdown
	         ERROR: YOUR SITE COULD NOT BE BUILT:
	                ------------------------------------
	                Missing dependency: kramdown

I had kramdown installed (verified through 'gem list'). I looked through several articles and the solution that finally worked was this.

	~$bundle clean --force

I was also having problems with regeneration of the site after making changes while the jekyll server was running. I was getting this error:

	GitHub Metadata: No GitHub API authentication could be found. Some fields may be missing or have incorrect data.

	Error: SSL_connect returned=1 errno=0 state=SSLv3 read server certificate B: certificate verify failed

	Error: Run jekyll build –trace for more information.

I followed the tutorial here:
https://www.hieule.info/programming/fix-errors-github-metadata-ssl-certificate-running-jekyll-serve/

Note that I had to restart my pc to get this fix working with GitBash. It worked right away with the Windows CMD prompt.