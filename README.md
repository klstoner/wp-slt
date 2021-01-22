# wp:slt
Web Publishing : Simple Little Thing
CREATED: 2 Jan 2021
UPDATED: 5 Jan 2021
UPDATED: 6 Jan 2021
UPDATED: 21 Jan 2021

_INTRO_

This little web publishing / blogging app is a very simple front-end for people who want to write and publish online, without needing to learn all the complexities of today's blogging platforms. 

The goal of wp:slt (or, wp-slt as it's named on github - since they won't let me use a colon) is to make publishing blog posts and simple web pages an everyday reality for everyone who wants to do it. 

Plus, it's a great way to learn the basics of building websites, from FTP and navigating directories, to learning simple HTML, CSS, and JavaScript. wp:slt lets you do all that. 

_WARRANTIES AND GUARANTEES_
There are none. This app is PHP-based, and it generates pages on your server. You are responsible for your own security, as well as ensuring the hygiene of your own site / app(s). If someone gains unauthorized access, they can post all manner of things to your site that you probably don't want there. So, be careful. And be mindful of security at all times. 

_BACKGROUND_

When I got started building websites back in 1995, it was much more possible and practical, than it is today.

Over the years, CMS developers have made tremendous strides in terms of evolving and maturing our platforms. Unfortunately, this increasing complexity (while fun for many of us) can be a gating factor for those just getting started... or those who just don't have a lot of discretionary time to learn how to change settings and configure stuff 'n' whatnot.

Plus, it kinda sucks all the joy out of the promise of a content management system we embrace, in order to publish quickly and easily. When you have to adjust all sorts of settings, enable plugins, fiddle with reading and writing features, and then have to curate comments or worry about database issues, you can easily spend a fair amount of your time fiddling with all that... when what you really wanted to do, was just... write and publish quickly to the web.

Never doubt me when I say, it was simpler to publish online, all those years ago. 

With wp:slt, it can be again.

_REQUIREMENTS_

To run wp:slt, you need to have
- A server that runs PHP (on the internet or a local server using WAMP or XAMPP)
- An FTP client
- A web browser with either access to the internet or the local server where you're running the app (WAMP or XAMPP)

_OPTIONAL_

- A text editor to create/update the page template(s), script(s), and css file(s)
- A working knowledge of simple html (for embellishing your content) or a willingness to learn
- A graphics program to create, edit and properly format images for your site

_HOW TO SET IT UP_

1. Okay, first you want to download a zip file of wp:slt from https://github.com/klstoner/wp-slt
 - I'm not going to put all the individual files up there - you can download the zip file

2. Unzip it into a directory on your computer
 - If you don't know how to do that, now's a great time to learn. Google can show you.
 - Make sure you keep a copy of the original .zip file, in case you need to revert any of the pages/code back in the future

3. Update the following elements in a text editor. When you're done, make sure they save with the .php extension. Some text editors will put .txt on the end. Just take that off and you'll have .php files.
- The top-level index.php file -- change the text there to what you want it to say. This is your index page. You can have it look any way you like. Note that I've included a dynamic pages list that shows all the content. You can comment this out or remove it.
- /update/update.php -- you need to change the system password 1234poiu to something else that you want
	# vvvvv Define the system password below vvvvv
		$loginSystemPwd = "1234poiu";
- /includes/header.php -- this is the header. You'll need to know just a bit of html to update it.
- /includes/footer.php --  this is the header. You'll need to know just a bit of html to update it.

 
4. Place the entire contents of wp:slt onto a web server 
 - If running externally on the internet, you'll need to get the files on the server
 	- If you can FTP all the files and directory structure together, that's great - it makes your life easier
		- Again, if you don't know how to do that, now's a great time to learn. Google can show you.
	- If your host makes you create each directory and upload each file manually, then make sure the directory structure and files are set up as detailed in #5 below.
 - If you're running wp:slt locally, you can just place all the files in the directory where you'll be running the app

5. Check the directory structure. It must look like this:

	index.php // top level index page that's your landing page
	gnu3-gpl-license.txt // standard license for this
	readme.txt // this file
	release-notes.txt // notes about what's changed since the last time I updated this system

 	assets/	
 		favicon.png // favicon that you can replace with another image of your liking
 		scripts.js // placeholder file for any scripts you want to add later, can be updated with a text editor
 		styles.css // styles for both the editing page(s) and the content on your new site, can be updated with a text editor
 	
	content/
		sample-page.php // just a sample page to start with - you should remove it after you're up and running
				// so it doesn't show up in your table of contents
				// note: some other pages may be in there, you can do what you like with them
	
	includes/
		footer.php // the site footer, can be updated with a text editor
		header.php // the site header with navigation links, can be updated with a text editor
		toc.php // dynamically generated table of contents listing all the pages on your site
		ids.txt // this specifies the id that will enclose the body content. later, it may be expanded to include multiple ones, but for now, there's just one
	
	templates/
		index.php // starting template for your site, can be updated with a text editor, but 
			  // there are portions of html that MUST NOT BE CHANGED, or you will break wp:slt
	
	update/
		index.php // login page where you enter the password you specified as your system password
		createpage.php // page creator and toc updating scripts, also shows confirmation that a page was created
		update.php // main update screen where you can create a new page or you can choose an existing page to edit
		
	
 
6. (OPTIONAL) Set a password for the /update/directory so you can double-block people from possibly updating your site. 
WARNING! DANGER! ALERT!!!
--> IF YOU DO NOT DO THIS, ANYBODY - AND I MEAN ANYBODY - CAN GET TO OUR LOGIN PAGE AND POTENTIALLY HACK OR UPDATE YOUR SITE!!
WARNING! DANGER! ALERT!!!
 - You can typically do this via settings on the web host. Check with your hosting service about how to do this.
 - NOTE: In the future I may be adding a password feature, but for now, just set it with your host. Or use it locally on a server on your own machine, and then FTP the pages to your internet site.

7. Go to [yourdomain]/update/ and login. From there, you can create new pages to your heart's content.

8. When you've published your page, the table of contents will update.


Watch this space for more updates - I got the first version working with create / update capabilities, and I'm going to let it rest overnight, to make sure I'm not missing anything. I mean, I probably have missed something, and I'll have to fix it later, but I want it to at least work well, right out of the gate. Accessibility means not breaking into a million different pieces, just 'cause you look at something sideways.
