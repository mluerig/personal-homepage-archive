---
title: Hosting static websites with github pages and jekyll
date: 2021-11-15 
tag-name: tech tutorials
description: How to host and easily maintain personal or lab-websites using github pages and jekyll.
og_image: /assets/images/posts/demo-hp-2.png
---

*This is a series of posts where I document some of the techy things I do for my work as a scientist. My motivation for these posts is to both document the procedures for myself and help share them among the science community. My goal is to focus on writing more posts rather than making each post all-encompassing, but if I am missing relevant information please do let me know and I will add it.*

I like the concept of a personal website to feature scientific interests, resources, or other relevant information related to working as a scientist. What I don't like is spending a lot of time manging content or dealing with bloated and unflexible website management systems, like wordpress. 

With [github-pages](https://pages.github.com/){:target="_blank"}, a website and its content can be easily hosted and managed through a regular github repository - just like the one you are looking at right now. Together with [jekyll](https://jekyllrb.com/){:target="_blank"}, a generator for static websites that uses [markdown](https://www.markdownguide.org/getting-started/){:target="_blank"}, content management becomes incredibly simple. Here is a short introduction to get a website up and running in a few minutes. 

For all the presented methods you will need a github account. 

For additional guides (e.g. how to connect this do your own custom domain) and for links to free themes, see the end of this post.

# The simple way: adding content on github.com

This is more of a proof of principle, illustrating where the website content is hosted and how markdown syntax translates into a website. For building a personal or lab-website from scratch, you may want to use the one of the other methods introduced below.

1. Log into your github account and make a new public repo without any files - I call mine `my-demo-homepage-1`.

2. Go to Settings > Pages > Choose a theme - I chose "minimal". Click the "Select theme" button".

	<div class="res-center">
	<div class="res-container">
	<img class="res-img" src="/assets/images/posts/gh-pages.png">
	</div>
	</div>

3. Add some more meaningful text to replace the default readme - I added this:

        # Demo-homepage of Moritz Lürig

		This is a demonstration of how simple, aesthetic and informative websites can be generated using github pages and jekyll. 

		More information can be found at [my actual webpage](https://www.luerig.net/posts/website-with-gh-pages).

		Thanks for visiting :-) 
		
4. Done - now you can see your page under https://[USERNAME].github.io/[REPONAME] - mine is at [https://mluerig.github.io/my-demo-homepage-1/](https://mluerig.github.io/my-demo-homepage-1/)


# The better way: fork-clone-edit-push

This might be the most convient method for most people. Here, an existing jekyll theme is forked and cloned to your local computer, where you can edit it with your favorite text editor, and then push the changes to the forked repo. 

1. Install git on your machine - see [this guide](https://github.com/git-guides/install-git). 

2. Log into your github account.

3. Go to the minimal jekyll theme repo: 

    [https://github.com/pages-themes/minimal](https://github.com/pages-themes/minimal)

4. Fork the repo, and rename it if you'd like - I name this one `my-demo-homepage-2`.

5. Clone the repo to your local computer:

		git clone https://github.com/mluerig/my-demo-homepage-2
		
6. Open the repo and edit `index.md` - I'll add the same text as above. In addition, I will add a flashly logo. The logo is not directly linked through `index.md`, but through `config.yaml`, which can be used to control many other settings and content. I am changing the content of config.yaml to:

		title: Look - I made website!
		logo: /assets/img/logo.gif
		theme: jekyll-theme-minimal

	The new [logo](https://knowyourmeme.com/memes/brent-rambo) needs to be added to `/assets/img/`. 
	
7. Add changes to git, commit and push:

		git add .
		git commit -m "new intro text / new logo"
		git push


8. Open the repo on github,  go to Settings > Pages > Source and choose the master branch, which will publish the repo under: 
	
	[https://mluerig.github.io/my-demo-homepage-2/](https://mluerig.github.io/my-demo-homepage-2/)

	<div class="res-center">
	<div class="res-container">
	<img class="res-img" src="/assets/images/posts/demo-hp-2.png">
	</div>
	</div>

# The involved way: installing jekyll on your local machine

This is assuming that you have already forked or made your own gh-pages repo to work with. 

1. Install [Jekyll](https://jekyllrb.com/docs/installation/){:target="_blank"} on your local machine: 
	- download and install Ruby (a high-level programming language) - simply follow the [instructions on the Ruby community website](https://www.ruby-lang.org/en/downloads/){:target="_blank"}
	- update gems, Ruby's package management system: `gem update`
	- GCC need to be installed and your system. On Windows, if you install Ruby through the ruby installer, GCC will become available through the MSYS2 devkit installed after the Ruby installation - simply hit "Enter" when you see this: 
	
	<div class="res-center">
	<div class="res-container">
	<img class="res-img" src="/assets/images/posts/msys2_win.png">
	</div>
	</div>
	
	- Make needs to be installed on your system. On Windows, you can use chocolatey ([install first](https://chocolatey.org/install){:target="_blank"}): `choco install make`
	- test installations: `jekyll -v`, `ruby -v`, `make -v`
	
	
2. clone/pull your current repo. 

3. Run bundle to install or update the dependencies specified in your gemfile:

		bundle install 
		bundle update

4. Now you can preview your edits on your local computer using `bundle exec jekyll serve` under `http://127.0.0.1:4000/`

5. Edit some markdown files in the repo and save them. If you refresh the page in the browser, you should see the updates immediately on your local machine. This way you can experiment with more involved changes and edits before exposing them to the public. However, note that for any changes to `_config.yaml`, you need to termiante the current serving session and restart it with `bundle exec jekyll serve`.


# Additional resources

- [Using a custom domain instead of .github.io](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages)
- [Using Jekyll with Bundler](https://jekyllrb.com/tutorials/using-jekyll-with-bundler/)


# Free jekyll themes
- [https://github.com/topics/jekyll-theme](https://github.com/topics/jekyll-theme)
- [https://jekyllthemes.io/free](https://jekyllthemes.io/free)
- [https://jekyll-themes.com/free/](https://jekyll-themes.com/free/)
- [https://jamstackthemes.dev/ssg/jekyll/](https://jamstackthemes.dev/ssg/jekyll/)
