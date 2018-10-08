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
| **cost over all** | $4 or less a year for domain



I see some possible directions you could go to create a blog about programming. If you belive me I really found the best setup, skip next several chapters and go the the "Static Site Generator". If you want to know a bit more about my journey, just keep reading the whole article.

## Popular CMS like Wordpress or GHost
That was actually where my jurney initialy begun. Use one of the popular CMS seemed like the right way to go to be able to start work on the content right away with configuration and development effort. 

But I was surprised a lot by the super-crazy pricing policy of these services. Wordpress.com costs around $400 a year, Ghost is even slighly more pricy. So to create an account directly in a branded CMS was not a way due to the very high price for a non-profit blog.

At this point it was already clear that if to use any of the open source CMS, it would be Wordpress. Other CMS didn't have Markdown support.

Branded accouts were too expensive, but there can be found hosting providers on the market which offers deploying a custom instance for much acceptable price, around $180 a year.

Seemed like that could be it, houndreds of blog templates available, thousands of plug-ins. And after couple of clicks you can start to work on your content right away, your blog is already finished on 95%.

But unfortunatelly as I later found out, to finish this last 5% can result in terrible pain, especially if you are not a PHP guy :). But the biggest blocker out of all was the lack of a good Markdown editor with syntax highlighting feature. 

Well, I found a one after all, a very good one, but still not perfect. Some of the 3rd party sources it was referencing couldn't get along with my plans to run my website on HTTPS.
On top of that, the development of this plug-in was discontinued.

Also customizing templates and overall tweeking the application was resulting into the big time waste for even very elementar modifications.

This was first time I realized that completly custom solution based on technologies much closer to my knowledge could be a better was. I was nearly there, but made a manager decision to drop the Wordpress completly.

It's possibly a good platform if you want to blog about clothes or lipsticks, but for a blog about programming is it not.

## Own/Custom project
Well, it's a bit of work, but you are a software developer, you should be able to develop a blog of your own. 

You need a good in Javascript written Markdown editor, simple layer on a web server converting the Markdown into HTML and of couse a database. The very last step would be to give it a design.

All this is quite easy possible from the developing point of view, but deployment is a bit more complicated situation.

If you chose to deploy your database and webserver into an own server, this is gonna be cheapest solution, you could end up on $100 a year or maybe even a bit less. But the mayor pitfall here is the time you'll have to spend on the configuration and maintenance. You'll have to take care of all the security updates, sometimes it all gonna go offline because your provider make the server restart and your services are not going to come back up. Sometimes an update after couple of years cause incompatibility with your code and so on.

More care-free solution would be to use cloud services. Its configuration-less and care-free. One DB service and one Web app do the trick, fast deployed and no care. But you are going to end up on something like $25 a month and this is really a lot for a blog.

But then I came across one technology...

## Static Site Generator
I still cannot 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY1ODY3NDc0MSwxNzY2MjM4NTgxLDEwOD
g1OTA2ODQsMTI5MDk5OTE2NV19
-->