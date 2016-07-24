# Ruby on Rails Tutorial

## Learn Web Development with Rails

Ref: [Learn Web Development with Rails](https://www.railstutorial.org/book)

### Content

<ul>
	<li><a href="#from-zero">From zero to deploy</a>
		<ul>
			<li><a href="#intro">Introduction</a></li>
			<li><a href="#upand">Up and Running</a></li>
			<li><a href="#thefirst">The first application</a></li>
		</ul>
	</li>

	<li>...</li>
</ul>

## Chapter 1

<h3 id="from-zero">From zero to deploy</h3>

Welcome to Ruby on Rails Tutorial: Learn Web Development with Rails. The purpose of this book is to teach you how to develop custom web applications, and our tool of choice is the popular Ruby on Rails web framework. In addition to focusing on general principles of web development (rather than on Rails specifically), the Ruby on Rails Tutorial teaches the broader skill of technical sophistication (Box 1.1),1 which is a principal theme developed by the Learn Enough to Be Dangerous tutorials.2 In particular, the Learn Enough introductory sequence consists of a series of tutorials that are suitable as prerequisites to the Ruby on Rails Tutorial, starting with Learn Enough Command Line to Be Dangerous,3 which (unlike the present tutorial) is aimed at complete beginners.

Box 1.1. Technical sophistication (Canggih)

> The Ruby on Rails Tutorial is part of the Learn Enough to Be Dangerous family of tutorials, which develop the theme of technical sophistication: the combination of hard and soft skills that make it seem like you can magically solve any technical problem (Figure 1.1). Web development, and computer programming in general, are essential components of technical sophistication, but there’s more to it than that—you also have to know how to click around menu items to learn the capabilities of a particular application, how to clarify a confusing error message by Googling it, or when to give up and just reboot the darn thing.

> Because web applications have so many moving parts, they offer ample (cukup) opportunities to develop your technical sophistication. In the context of Rails web development, some specific examples of technical sophistication include making sure you’re using the right Ruby gem versions, running bundle install or bundle update, and restarting the local webserver if something doesn’t work. (Don’t worry if all this sounds like gibberish; we’ll cover everything mentioned here in the course of completing this tutorial.)

> As you proceed through this tutorial, in all likelihood you will occasionally be tripped up by things not immediately working as expected. Although some particularly tricky steps are explicitly highlighted in the text, it is impossible to anticipate all the things that can go wrong. I recommend you embrace these inevitable stumbling blocks as opportunities to work on improving your technical sophistication. Or, as we say in geek speak: It’s not a bug, it’s a feature!

The Ruby on Rails Tutorial is designed to give you a thorough introduction to web application development, including a basic grounding in Ruby, Rails, HTML & CSS, databases, version control, testing, and deployment—sufficient to launch you on a career as a web developer or technology entrepreneur. If you already know web development, this book will quickly teach you the essentials of the Rails framework, including MVC and REST, generators, migrations, routing, and embedded Ruby. In any case, when you finish the Ruby on Rails Tutorial you will be in a position to benefit from the many more advanced books, blogs, and screencasts that are part of the thriving (berkembang) programming educational ecosystem.4

The Ruby on Rails Tutorial takes an integrated approach to web development by building three example applications of increasing sophistication, starting with a minimal hello app (Section 1.3), a slightly more capable toy app (Chapter 2), and a real sample app (Chapter 3 through Chapter 14). As implied by their generic names, the applications developed in the Ruby on Rails Tutorial are not specific to any particular kind of website. The final sample application bears more than a passing resemblance (kemiripan) to Twitter (which, coincidentally (secara kebetulan)
, was also originally written in Rails), but the emphasis throughout the tutorial is on general principles, so you will have a solid foundation no matter what kinds of web applications you want to build.

In this first chapter, we’ll get started with Ruby on Rails by installing all the necessary software and by setting up our development environment (Section 1.2). We’ll then create our first Rails application, called hello_app. The Rails Tutorial emphasizes (menekankan) good software development practices, so immediately after creating our fresh new Rails project we’ll put it under version control with Git (Section 1.4). And, believe it or not, in this chapter we’ll even put our first app on the wider web by deploying it to production (Section 1.5).

In Chapter 2, we’ll make a second project, whose purpose is to demonstrate the basic workings of a Rails application. To get up and running quickly, we’ll build this toy app (called toy_app) using scaffolding (Box 1.2) to generate code; because this code is both ugly and complex, Chapter 2 will focus on interacting with the toy app through its URIs (often called URLs)5 using a web browser.

The rest of the tutorial focuses on developing a single large real sample application (called sample_app), writing all the code from scratch. We’ll develop the sample app using a combination of mockups, test-driven development (TDD), and integration tests. We’ll get started in Chapter 3 by creating static pages and then add a little dynamic content. We’ll take a quick detour in Chapter 4 to learn a little about the Ruby language underlying Rails. Then, in Chapter 5 through Chapter 12, we’ll complete the foundation for the sample application by making a site layout, a user data model, and a full registration and authentication system (including account activation and password resets). Finally, in Chapter 13 and Chapter 14 we’ll add microblogging and social features to make a working example site.

Box 1.2. Scaffolding: Quicker, easier, more seductive (Menggoda)

> From the beginning, Rails has benefited from a palpable (gamblang) sense of excitement, starting with the famous 15-minute weblog video by Rails creator David Heinemeier Hansson. That video and its successors are a great way to get a taste of Rails’ power, and I recommend watching them. But be warned: they accomplish their amazing fifteen-minute feat using a feature called scaffolding, which relies heavily on generated code, magically created by the Rails generate scaffold command.

> When writing a Ruby on Rails tutorial, it is tempting to rely on the scaffolding approach—it’s quicker, easier, more seductive. But the complexity and sheer (semata) amount of code in the scaffolding can be utterly overwhelming (benar2 luar biasa) to a beginning Rails developer; you may be able to use it, but you probably won’t understand it. Following the scaffolding approach risks turning you into a virtuoso (ahli pemain musik) script generator with little (and brittle) (rapuh) actual knowledge of Rails.

> In the Ruby on Rails Tutorial, we’ll take the (nearly) polar opposite approach: although Chapter 2 will develop a small toy app using scaffolding, the core of the Rails Tutorial is the **sample app**, which we’ll start writing in **Chapter 3**. At each stage of developing the sample application, we will write small, bite-sized pieces of code—simple enough to understand, yet novel enough to be challenging. The cumulative effect will be a deeper, more flexible knowledge of Rails, giving you a good background for writing nearly any type of web application.

<h3 id="intro">1.1 Introduction</h3>

Ruby on Rails (or just “Rails” for short) is a web development framework written in the Ruby programming language. Since its debut in 2004, Ruby on Rails has rapidly become one of the most powerful and popular tools for building dynamic web applications. Rails is used by companies as varied as Airbnb, Basecamp, Disney, GitHub, Hulu, Kickstarter, Shopify, Twitter, and the Yellow Pages. There are also many web development shops that specialize in Rails, such as ENTP, thoughtbot, Pivotal Labs, Hashrocket, and HappyFunCorp, plus innumerable independent consultants, trainers, and contractors.

What makes Rails so great? First of all, Ruby on Rails is 100% open-source, available under the generous MIT License, and as a result it also costs nothing to download or use. Rails also owes much of its success to its elegant and compact design; by exploiting the malleability of the underlying Ruby language, Rails effectively creates a domain-specific language for writing web applications. As a result, many common web programming tasks—such as generating HTML, making data models, and routing URLs—are easy with Rails, and the resulting application code is concise and readable.

Rails also adapts rapidly to new developments in web technology and framework design. For example, Rails was one of the first frameworks to fully digest and implement the REST architectural style for structuring web applications (which we’ll be learning about throughout this tutorial). And when other frameworks develop successful new techniques, Rails creator David Heinemeier Hansson and the Rails core team don’t hesitate to incorporate their ideas. Perhaps the most dramatic example is the merger of Rails and Merb, a rival Ruby web framework, so that Rails now benefits from Merb’s modular design, stable API, and improved performance.

Finally, Rails benefits from an unusually enthusiastic and supportive community. The results include thousands of open-source contributors, fun and informative conferences, a huge number of gems (self-contained solutions to specific problems such as pagination and image upload), a rich variety of informative blogs, and a cornucopia of discussion forums and IRC channels. The large number of Rails programmers also makes it easier to handle the inevitable application errors: the “Google the error message” algorithm nearly always produces a relevant blog post or discussion-forum thread.

#### 1.1.1 Prerequisites

There are no formal prerequisites to this book, and the Ruby on Rails Tutorial contains integrated tutorials not only for Rails, but also for the underlying Ruby language, the default Rails testing framework (minitest), the Unix command line, HTML, CSS, a small amount of JavaScript, and even a little SQL. That’s a lot of material to absorb, though, and I generally recommend having some HTML and programming background before starting this tutorial. If you’re new to software development, I recommend starting with the tutorials at Learn Enough to Be Dangerous instead:

Developer Fundamentals

1. Learn Enough Command Line to Be Dangerous
2. Learn Enough Text Editor to Be Dangerous
3. Learn Enough Git to Be Dangerous

Web Basics

1. Learn Enough HTML to Be Dangerous
2. Learn Enough CSS & Layout to Be Dangerous
3. Learn Enough JavaScript to Be Dangerous

Intro Ruby Web Development

1. Learn Enough Ruby to Be Dangerous
2. Learn Enough Sinatra to Be Dangerous
3. Learn Enough Ruby on Rails to Be Dangerous

Professional Ruby Web Development

* The Ruby on Rails Tutorial

One common question when learning Rails is whether to learn Ruby first. The answer depends on your personal learning style and how much programming experience you already have. If you prefer to learn everything systematically from the ground up, or if you have never programmed before, then learning Ruby first might work well for you, and in this case I recommend following the full Learn Enough sequence listed above. On the other hand, many beginning Rails developers are excited about making web applications, and would rather not wait to finish a whole book on Ruby before ever writing a single web page. In this case, I recommend giving this tutorial a go and switching to the Learn Enough sequence if it proves too challenging.

At the end of this tutorial, no matter where you started, you should be ready for the many more intermediate-to-advanced Rails resources out there. Here are some I particularly recommend:

* The Learn Enough Society: Premium subscription service that includes a special enhanced version of the Ruby on Rails Tutorial book and 15+ hours of streaming screencast lessons filled with tips, tricks, and live demos that you can’t get from reading a book. Also includes text and videos for the other Learn Enough tutorials. You have to solve a puzzle to join, and scholarship discounts are also available.
* Code School: Good interactive online programming courses
* The Turing School of Software & Design: a full-time, 27-week training program in Denver, Colorado
* Bloc: an online bootcamp with a structured curriculum, personalized mentorship, and a focus on learning through concrete projects. Use the coupon code BLOCLOVESHARTL to get $500 off the enrollment fee.
* Launch School: A good online Rails development bootcamp (includes advanced material)
* Firehose Project: A mentor-driven, online coding bootcamp focused on real-world programming skills like test-driven development, algorithms, and building an advanced web application as part of an agile team. Two-week free intro course.
* Thinkful: An online class that pairs you with a professional engineer as you work through a project-based curriculum
* Pragmatic Studio: Online Ruby and Rails courses from Mike and Nicole Clark. Along with Programming Ruby author Dave Thomas, Mike taught the first Rails course I took, way back in 2006.
* RailsApps: A large variety of detailed topic-specific Rails projects and tutorials
* Rails Guides: Topical and up-to-date Rails references

#### Exercises

The Ruby on Rails Tutorial contains a large number of exercises. Solving them as you proceed through the tutorial is strongly recommended.

In order to keep the main discussion independent of the exercises, the solutions are not generally incorporated into subsequent code listings. (In the rare circumstance that an exercise solution is used subsequently, it is explicitly solved in the main text.) This means that over time your code may diverge (menyimpang) from the code shown in the tutorial due to differences introduced in the exercises. Learn how to resolve such discrepancies is a valuable exercise in technical sophistication (Box 1.1).

To record your answers and see solutions, you can join the Learn Enough Society, a subscription service from Learn Enough to Be Dangerous that includes a special enhanced version of the Ruby on Rails Tutorial.

Many of the exercises are challenging, but we’ll start out with some easy ones just to get warmed up:

1. Which website hosts the Ruby gem for Ruby on Rails? Hint: When in doubt, Google it.
2. What is the current version number of Rails?
3. As of this moment, how many total times has Ruby on Rails been downloaded?

#### 1.1.2 Conventions used in this book

The conventions used in this book are mostly self-explanatory. In this section, we’ll go over some that may not be.

Many examples in this book use command-line commands. For simplicity, all command line examples use a Unix-style command line prompt (a dollar sign), as follows:

	$ echo "hello, world"
	hello, world

Rails comes with many commands that can be run at the command line. For example, in Section 1.3.2 we’ll run a local development webserver with the rails server command:

	$ rails server

As with the command-line prompt, the Rails Tutorial uses the Unix convention for directory separators (i.e., a forward slash /). For example, the sample application production.rb configuration file appears as follows:

	config/environments/production.rb

This file path should be understood as being relative to the application’s root directory, which will vary by system; on the cloud IDE (Section 1.2.1), it looks like this:

	/home/ubuntu/workspace/sample_app/

Thus, the full path to production.rb is

	/home/ubuntu/workspace/sample_app/config/environments/production.rb

I will typically omit (menghilangkan) the application path and write just config/environments/production.rb for short.

The Rails Tutorial often shows output from various programs. Because of the innumerable (banyak sekali) small differences between different computer systems, the output you see may not always agree exactly with what is shown in the text, but this is not cause for concern. In addition, some commands may produce errors depending on your system; rather than attempt the Sisyphean task of documenting all such errors in this tutorial, I will delegate to the “Google the error message” algorithm, which among other things is good practice for real-life software development (Box 1.1). If you run into any problems while following the tutorial, I suggest consulting the resources listed in the Rails Tutorial help page.7

*Because the Rails Tutorial covers testing of Rails applications*, it is often helpful to know if a particular piece of code causes the test suite to fail (indicated by the color red) or pass (indicated by the color green). For convenience, code resulting in a failing test is thus indicated with red, while code resulting in a passing test is indicated with green.

Finally, for convenience the Ruby on Rails Tutorial adopts two conventions designed to make the many code samples easier to understand. First, some code listings include one or more highlighted lines, as seen below:

	class User < ApplicationRecord
	  validates :name,  presence: true
	  validates :email, presence: true
	end

Such highlighted lines typically indicate the most important new code in the given sample, and often (though not always) represent the difference between the present code listing and previous listings. Second, for brevity and simplicity many of the book’s code listings include vertical dots, as follows:

	class User < ApplicationRecord
	  .
	  .
	  .
	  has_secure_password
	end

These dots represent omitted code and should not be copied literally.

<h3 id="upand">1.2 Up and running</h3>

Even for experienced Rails developers, installing Ruby, Rails, and all the associated supporting software can be an exercise in frustration. Compounding the problem is the multiplicity of environments: different operating systems, version numbers, preferences in text editor and integrated development environment (IDE), etc. The Ruby on Rails Tutorial offers two recommended solutions to this problem. One possibility is to follow the full Learn Enough intro sequence mentioned in Section 1.1.1, which will automatically lead to a system configured for this tutorial.

The other possibility, recommended for newer users, is to sidestep such installation and configuration issues by using a cloud integrated development environment, or cloud IDE. The cloud IDE used in this tutorial runs inside an ordinary web browser, and hence (karenanya) works the same across different platforms, which is especially useful for operating systems (such as Windows) on which Rails development has historically been difficult. It also maintains the current state of your work, so you can take a break from the tutorial and come back to the system just as you left it.

#### 1.2.1 Development environment

Considering various idiosyncratic (istimewa) customizations, there are probably as many development environments as there are Rails programmers. To avoid this complexity, the Ruby on Rails Tutorial standardizes on the excellent cloud development environment [Cloud9.](http://c9.io/) In particular (khusus) , I am pleased to be partnering with Cloud9 to offer a free development environment specifically tailored to the needs of this tutorial. The resulting Rails Tutorial Cloud9 workspace comes pre-configured with most of the software needed for professional-grade Rails development, including Ruby, RubyGems, Git. (Indeed, the only big piece of software we’ll install separately is Rails itself, and this is intentional (Section 1.2.2).)

The cloud IDE also includes the three essential components needed to develop web applications: a text editor, a filesystem navigator, and a command-line terminal (Figure 1.2). Among other features, the cloud IDE text editor supports the “Find in Files” global search that I consider essential to navigating any large Ruby or Rails project.8 Finally, even if you decide not to use the cloud IDE exclusively in real life (and I certainly recommend learning other tools as well), it provides an excellent introduction to the general capabilities of text editors and other development tools.

![IDE anatomy](http://res.cloudinary.com/medio/image/upload/v1469377950/ide-anatomi_esirr4.png)

<center>Figure 1.2: The anatomy of the cloud IDE.</center>

Here are the steps for getting started with the cloud development environment:

1. Sign up for a free account at Cloud9.9 In order to prevent abuse, Cloud9 requires a valid credit card for signup, but the Rails Tutorial workspace is 100% free, and your card will not be charged.
2. Click on “Go to your Dashboard”
3. Select “Create New Workspace”
4. As shown in Figure 1.3, create a workspace called “rails-tutorial” (not “rails_tutorial”), set it to “Private to the people I invite”, and select the icon for the Rails Tutorial (not the icon for Ruby on Rails)
5. Click “Create workspace”
6. After Cloud9 has finished provisioning the workspace, it should start automatically

Because using two spaces for indentation is a near-universal convention in Ruby, I also recommend changing the editor to use two spaces instead of the default four. As shown in Figure 1.4, you can do this by clicking the gear icon in the upper right and then selecting “Code Editor (Ace)” to edit the “Soft Tabs” setting. (Note that this takes effect immediately; you don’t need to click a “Save” button.)

![Figure 1.3](http://res.cloudinary.com/medio/image/upload/v1469377132/cloud9_new_workspace_4th_ed_iqc2xe.png)

<center>Figure 1.3: Creating a new workspace at Cloud9.</center>

![Figure 1.4](http://res.cloudinary.com/medio/image/upload/v1469377804/cloud9_two_spaces_onwwx5.png)

<center>Figure 1.4: Setting Cloud9 to use two spaces for indentation</center>

#### 1.2.2 Installing Rails

The development environment from Section 1.2.1 includes all the software we need to get started except for Rails itself. To install Rails, we’ll use the gem command provided by the RubyGems package manager, which involves typing the command shown in Listing 1.1 into your command-line terminal. (If developing on your local system, this means using a regular terminal window; if using the cloud IDE, this means using the command-line area shown in Figure 1.2.)

Listing 1.1: Installing Rails with a specific version number.

	$ gem install rails -v 5.0.0

Here the -v flag ensures that the specified version of Rails gets installed, which is important to get results consistent with this tutorial.

<h3 id="thefirst">1.3 The first application</h3>

Following a long tradition in computer programming, our goal for the first application is to write a “hello, world” program. In particular, we will create a simple application that displays the string “hello, world!” on a web page, both on our development environment (Section 1.3.4) and on the live web (Section 1.5).

Virtually all Rails applications start the same way, by running the rails new command. This handy command creates a skeleton Rails application in a directory of your choice. To get started, users not using the Cloud9 IDE recommended in Section 1.2.1 should make a workspace directory for your Rails projects if it doesn’t already exist (Listing 1.2) and then change into the directory. (Listing 1.2 uses the Unix commands cd and mkdir; see Box 1.3 if you are not already familiar with these commands.)

Listing 1.2: Making a workspace directory for Rails projects (unnecessary in the cloud).

	$ cd                  # Change to the home directory.
	$ mkdir workspace     # Make a workspace directory.
	$ cd workspace/       # Change into the workspace directory.

Box 1.3. A crash course on the Unix command line

> For readers coming from Windows or (to a lesser but still significant extent) Macintosh OS X, the Unix command line may be unfamiliar. Luckily, if you are using the recommended cloud environment, you automatically have access to a Unix (Linux) command line running a standard shell command-line interface known as Bash.

> The basic idea of the command line is simple: by issuing short commands, users can perform a large number of operations, such as creating directories (mkdir), moving and copying files (mv and cp), and navigating the filesystem by changing directories (cd). Although the command line may seem primitive to users mainly familiar with graphical user interfaces (GUIs), appearances are deceiving: the command line is one of the most powerful tools in the developer’s toolbox. Indeed, you will rarely see the desktop of an experienced developer without several open terminal windows running command-line shells.

> The general subject is deep, but for the purposes of this tutorial we will need only a few of the most common Unix command-line commands, as summarized in Table 1.1. For a more thorough introduction to the Unix command line, see the first of the Learn Enough tutorials, Learn Enough Command Line to Be Dangerous.10

	Description					Command					Example

	list contents				ls						$ ls -l
	
	make directory				mkdir <dirname>			$ mkdir workspace
	
	change directory			cd <dirname>			$ cd workspace/
	
	cd one directory up									$ cd ..
	
	cd to home directory								$ cd ~ or just $ cd
	
	cd to path incl. home dir							$ cd ~/workspace/
	
	move file (rename)			mv <source> <target>	$ mv foo bar
	
	copy file					cp <source> <target>	$ cp foo bar
	
	remove file					rm <file>				$ rm foo
	
	remove empty directory		rmdir <directory>		$ rmdir workspace/
	
	remove nonempty directory	rm -rf <directory>		$ rm -rf tmp/
	
	concatenate & display file 	cat <file>				$ cat ~/.ssh/id_rsa.pub
	contents

<center>Table 1.1: Some common Unix commands.</center>

The next step on both local systems and the cloud IDE is to create the first application using the command in Listing 1.3. **Note that Listing 1.3 explicitly includes the Rails version number as part of the command**. This ensures that the same version of Rails we installed in Listing 1.1 is used to create the first application’s file structure. (If the command in Listing 1.3 returns an error like “Could not find ’railties’”, it means you don’t have the right version of Rails installed, and you should double-check that you followed the command in Listing 1.1 exactly as written.)

Listing 1.3: Running rails new (with a specific version number).

	$ cd ~/workspace
	$ rails _5.0.0_ new hello_app

As seen at the end of Listing 1.3, running rails new automatically runs the bundle install command after the file creation is done. We’ll discuss what this means in more detail starting in Section 1.3.1.

Notice how many files and directories the rails command creates. This standard directory and file structure (Figure 1.5) is one of the many advantages of Rails: it immediately gets you from zero to a functional (if minimal) application. Moreover, since the structure is common to all Rails apps, you can immediately get your bearings when looking at someone else’s code.

A summary of the default Rails files appears in Table 1.2. We’ll learn about most of these files and directories throughout the rest of this book. In particular, starting in Section 5.2.1 we’ll discuss the app/assets directory, part of the asset pipeline that makes it easy to organize and deploy assets such as cascading style sheets and JavaScript files. 





