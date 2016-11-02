---
---

How to build your own blog on git base on another website

>###Tool: jekyll(local test), git
Base website <https://github.com/kubernetes/kubernetes.github.io>
<br />

###Set up base software for jekyll
#####Ruby
<http://www.ruby-lang.org/en/downloads/>
#####RubyGems
<http://rubygems.org/pages/download>
#####NodeJS
<http://nodejs.org/>
#####Python2.7
<https://www.python.org/downloads/><br />

	$gem install jekyll
	
__To see which version of base software you installed, you can find all those software packages in /usr/local/lib/ruby/gems/__

---

###Use your base website source to build your own website locally

#####For example

	$git clone https://github.com/kubernetes/kubernetes.github.io.git
	$cd kubernetes.github.io

Then you have all the resources you need to build a website base on kubernetes.io

You can check Gemfile for gem's package that kubernetes.io need.

	$vi Gemfile
	source "https://rubygems.org"
	gem "jekyll", "3.2.1"
	gem "jekyll-sass-converter", "1.3.0"
	gem "minima", "1.1.0"
	gem "kramdown", "1.11.1"
	gem "liquid", "3.0.6"
	gem "rouge", "1.11.1"
	gem "jemoji", "0.7.0"
	gem "jekyll-mentions", "1.2.0"
	gem "jekyll-redirect-from", "0.11.0"
	gem "jekyll-sitemap", "0.10.0"
	gem "jekyll-feed", "0.5.1"
	gem "jekyll-gist", "1.4.0"
	gem "jekyll-paginate", "1.1.0"
	gem "jekyll-coffeescript", "1.0.1"
	gem "jekyll-seo-tag", "2.0.0"
	gem "jekyll-github-metadata", "2.0.2"
	gem "listen", "3.0.6"
	gem "activesupport", "4.2.7"
	"Gemfile" 20L, 541C
	
Let's suppose that you didn't install all these software with a exactly right version.<br />
Don't worry about that, Gemfile.lock will get this handle. All you need to do is:

	$bundle install

This command will help you go through the softwares that  list in the Gemfile.lock, and install those right-version of softwares automatically.<br />
<br />
Then you can build your own website with jekyll:

	$jekyll build
	
If this command doesn't work, try this one:
	
	$bundle exec jekyll build 
	
	Configuration file: /Users/manyang/dev/goprojects/src/kubernetes/_config.yml
            Source: /Users/manyang/dev/goprojects/src/kubernetes
       Destination: /Users/manyang/dev/goprojects/src/kubernetes/_site
 	Incremental build: enabled
      Generating...
                    done in 31.628 seconds.
 	Auto-regeneration: disabled. Use --watch to enable.
 	

When you see "... Generating... done ...", that means your website is ready to work.<br />
If you want to see how your website looks like locally, try this:

	$jekyll serve
	
	Configuration file: /Users/manyang/dev/goprojects/src/kubernetes/_config.yml
	Configuration file: /Users/manyang/dev/goprojects/src/kubernetes/_config.yml
            Source: /Users/manyang/dev/goprojects/src/	kubernetes
       	Destination: /Users/manyang/dev/goprojects/src/	kubernetes/_site
 	Incremental build: enabled
      	Generating...
                    	done in 0.491 seconds.
 	Auto-regeneration: enabled for '/Users/manyang/dev/	goprojects/src/kubernetes'
	Configuration file: /Users/manyang/dev/goprojects/src/kubernetes/_config.yml
    	Server address: http://127.0.0.1:4000//
  	Server running... press ctrl-c to stop.	

Now you can open <http://localhost:4000> to see your website.
<br />

---
###Publish your website with github pages
1. Create a new repositry on github:<br />**yourname.github.io**(make sure to use your user name as the first part of your repositry'name)
2. **git clone** it into your local work space.
3. Back-up your repositry's .git folder
4. Move your base website's recources into your work space.
5. Remove .git in your work space which you just copy (if necessary)
6. Move your back-up .git folder back to your work space.
7. Push your new website

		$git add .
		$git commit
		$git push origin master
		
Now you can find your website just public on **yourname.github.io**

---

###Change the recources into your own
Now you have your github pages'blog and your local testing environment, you can create a website that actually belong to you with your own recource.<br />

- Documents' list are located in */_data*
- Documents' location is */docs*
- You can find tags' name in index.html and all those .html that included

Don't forget to commit and push your changes to your repositry when you're done with edit.


