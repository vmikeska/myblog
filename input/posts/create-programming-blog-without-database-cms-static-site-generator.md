Title: Create a programming blog without any database or CMS by a static site generator
Description: Don't drag into the project dependencies you don't need. Create a programming blog without any database or CMS by a static site generator using Markdown and Wyam with free hosting on Github pages
Published: 5/10/2018
Image: title-if.jpg
Tags: 
- static site generator
- markdown
- no database
- no cms
- wyam
- free hosting
- github pages
---

### Hey guys, just created a blog...
I spent most of my evenings in the last month setting up this blog. I have some fresh knowlede I want to share with you. When I was searching for and article to help me get started, the only I could find were the blog posts about the webhostings and Wordpress. As the programming blog is a bit specific type of blog, I decided write one of mine first posts about creating programming blogs.  

### ...I'd like to share with you how to setup a blog technically
The desired article I was searching for shouldn't have helped me with the content. The article should have helped me with the creation and technical setup.
The most important part of a blog is the content, so don't lose time on a flashy design.
Most successful blogs usually doesn't have very attractive design. Their design usually didn't experience a change in the last decade :)
This blog post aims at programmers seeking the info how to create the blog technically.

### What do you want
Your blog should have a second level domain (like myblog.com), all the technical necessities, minimal setup, minimal maintenance and running costs as low as possible.

### This post helps you to make a setup like this

| aspect | solution |
|--|--|
| url | Second level domain, HTTPS |
| features | Comments with Disqus, Addthis sharing and Full Markdown support|
| setup and deployment | Everything in one Sunday|
| security | Cannot be hacked, completly care-less|
| maintenance | None at all|
| backups | Without any effor|
| hosting cost | Completly for free|
| **cost over all** | Just your domain, $4 or less

## The options you have
I see some possible directions you could go to create a blog about programming. If you belive I found the best one, skip next several chapters and go the the **Static Site Generator**. If you want to know a bit more about my journey, just keep reading the whole article.

### Popular CMS like Wordpress or GHost
This is where my jurney initialy begun. Chose one of the popular CMS seemed like the right way to go. You just register and begin with the content right away, no excessive development, deployment and configuration. Just couple of clicks and your blog is 90% ready.

But as I later found out,  these last 10% is not an easy piece.

On top of that, I was surprised by the super-crazy pricing policy of these services. Wordpress.com costs around $400 a year, Ghost is even slighly more pricy. So to create an account directly in a branded CMS was not a way due to the very high price for a non-profit blog.

Altough at this point it was already clear that if to use any of the open source CMS, it would be Wordpress. Other CMS didn't have any promissing Markdown plugins, on the Wordpress I found at least one.

Branded accouts are too expensive, but there can be found hosting providers on the market which offers deploying a custom instance for much acceptable price, around $180 a year.

Seemed like that could be it, houndreds of blog templates available, thousands of plug-ins. And after couple of clicks you can start to work on your content right away.

As I already implied above, the last 10% of customization can result in a terrible pain. It multiplies if you are not a PHP guy :). 
The biggest blocker out of all was the lack of good and working Markdown plugin. 

Well, I found a one after all, not perfect, but a very good one. Some of the 3rd party sources it was referencing couldn't get along with my plans to run my website on HTTPS.
On top of that, the development of this plug-in was discontinued.

Also customizing templates and overall tweeking the application was resulting into the big time waste with every little modification.

At this point I realized that completly custom solution based on technologies much closer to my knowledge could be a better choice. I was nearly there, but made a manager decision to drop the Wordpress completly.

It's possibly a good platform if you want to blog about clothes or lipsticks, but for a blog about programming is it not.

## Own/Custom project
Well, it's a bit of work, but you are a software developer, you should be able to develop a blog of your own. 

Spoiler: It's not the way, skip to the next chapter, or keep reading if you want to review my steps.

You need a good in Markdown editor as a Javascript component, simple layer on a web server converting the Markdown into HTML and of couse a database for your content. The very last step would be to give it a design.

From the development point of view could be all this achived quite easy, but deployment, maintenance and running costs complicates the situation.

If you chose to deploy your database and webserver into an own server, this is gonna be cheapest solution.
You could end up on $100 a year or maybe even a bit less. But the mayor pitfall is the time you'll spend on the configuration and maintenance. 
You'll have to take care of all the security updates, sometimes is it all gonna go offline because your hosting provider restarts server and your services are might not come back. Sometimes an update after couple of years cause incompatibility with your code and so on.

More care-free solution would be to use cloud services. It's configuration-less and care-free. One DB service and one Web app do the trick, fast deployed and no care. But you are going to end up on something like $25 a month and this is really a lot for a blog.

But then I came across one technology...

## Static Site Generator
I couldn't belive I didn't know about this technology.
I realized how much I'm trapped in the world of the enterprise software development a have no clue that there is an enitre field about Static site generators.

Jekyll, the platform I came across is the leader and most popular in the field. Looked very promissing, but have poor support on Windows, so I decided to chose a technology based on a platform which is much closer to my knowlede, the .NET.

Wyam, the technology I used and the rest of article is going to be affected by it. 
But even if you decide for any other Static site generator, the principal should be prety much the same.

#### Markdown - the base of content
There must happen two things with the content you write. It must be somehow written and it must be somehow rendered.
The rendering at the end is going to be in HTML, there is not any other choise.
But to write you content directly in the HTML 

The content is base of the blog and must be somehow written. 

If you consider to become a blogger, If you haven't heard of Markdown yet, 




advantages
you can just grab your content and migrate to another platform based on Markdown within hours
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM5Mjk3MTEwNCwxMTM4MjA4MzAzLC0xMz
M3ODg2NTAyLDEzMDE5MzI0MDIsMTc2NjIzODU4MSwxMDg4NTkw
Njg0LDEyOTA5OTkxNjVdfQ==
-->