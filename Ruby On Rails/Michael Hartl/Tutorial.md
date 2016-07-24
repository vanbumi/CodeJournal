# Ruby on Rails Tutorial

## Learn Web Development with Rails

Ref: [Learn Web Development with Rails](https://www.railstutorial.org/book)

### Content

<ul>
	<li>...</li>
	<li>...</li>
</ul>

## Chapter 1

### From zero to deploy

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

### 1.1 Introduction

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