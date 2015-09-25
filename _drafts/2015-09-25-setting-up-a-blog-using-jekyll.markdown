---
layout: post
title: "Setting up a blog using Jekyll"
date: "2015-09-25"
tags: [jekyll, linux, wordpress]
---

As I described in the [first post]({% post_url 2015-09-24-a-new-blog %}) on this blog, I want to summarize what I did in order to get this  website up and running. But first I'm gonna write something about why I used the software that I used.

## Popularity of Wordpress
When you're the sysadmin of a webserver with many Wordpress websites, you know that sooner or later one of them is going to get compromised (well, the possibility of it happening is substantial). The fact that Wordpress itself is easy to install and that it can easily be extended using a plethora of plugins brought Wordpress to where it is right now. It is one of the most popular content management systems worldwide. Even though it was designed as (and in its core it still is) blogging software.

The immense popularity led to programmers and designers all over the world creating the most beautiful plugins and themes for Wordpress. Free and non-free. But what happens if there are people who offer certain themes for free, whereas you would have to pay tens of dollars on other websites? I'm not trying to condone piracy, but it is often a very attractive alternative! But what you always should keep in mind is where the pirated stuff is coming from. If I were to download some software using torrents or obscure websites, I would check it using antivirus software. But for Wordpress themes and plugins this is something almost nobody does, because it is something you just upload to a webserver.

But what happens if the "free" theme you downloaded is infected with malware which abuses the webserver by sending thousands of spam messages? Unfortunately this happens more often than you would like [^1].

The most obvious choice is to just use a different CMS, but the problem is more fundamental than that. Where complicated extensive website benefit from server-side scripting, for a simple blog this is often not necessary and badly written php-code is often a security threat. But on the other hand, creating a blog using only html-code is a very tedious job and would require a lot of maintenance when you add blog posts.

## Alternatives
So while I was browsing the web one day I stumbled upon a post describing **static site generators**. For me it described perfectly how a basic blog could be created. Content like blog posts and other pages are created on your normal pc or laptop using a regular editor (like notepad, atom or sublime text). Once your done writing your content, you can rebuild your website and within seconds your blog is up to date. The only other thing remaining is to upload the website to your hosting provider.

There are several benefits of this method of creating a website:

### Security
Since only html and javascript code is generated, there is no way of your server being compromised by malicious php scripts. So after the website has been generated locally, you upload a couple of html, css and js files (maybe even some pictures) and it's done.

### Performance
Even simple Wordpress websites start to respond slower when multiple users are browsing the website. The main contributors here are the MySQL-queries and the PHP processes. Now there are ways to improve this for Wordpress websites, but this requires several plugins and configuration time. For static websites however, even poor configured webservers can handle much more requests per second when compared to Wordpress websites.

### Working offline
Since the website is generated locally, this means that you can create content wherever you are. So if you're travelling by train or plane, you don't need to be connected to the outside world in order to see how your content looks in the browser. For instance, before I start typing in my text editor ([Atom](https://atom.io)) on my laptop, I run the following command in a terminal (also on my laptop)
`bundle exec jekyll serve --drafts`

which generates the website and tracks changes which are made to the files in the directory where the website is located. When a file changes, relevant pages are regenerated and can be viewed instantaneously.

## But which one?
So I decided fairly quickly that I wanted to try creating a blog using a static site generator. But as the header above says: _But which one?_

According to [staticsitegenerators.net](https://staticsitegenerators.net), there are 393 different generators, under different licenses and written in different languages.

Since I'm not that familiar in most of the mentioned languages (Ruby, Go, Coffeescript), I thought that all of them required somewhat of a learning curve. Therefore I left the language out of the equation.

So I sorted them based on 'Stars'. I don't really know what the stars mean, but I guess that the generators with more stars are more popular than other generators. At the time of writing, the difference between the number one and two is actually pretty big. The number one, Jekyll, had 21k stars, where the number two on the list Octopress (which was based on Jekyll iirc) had 9k stars.

After this very extensive field research, I decided to give Jekyll a go. Installation and configuration was actually pretty straightforward and hosting the website on GitHub is very easy. Writing in Markdown isn't that hard either.

But, the technical part will be described in a different post!

---
[^1]:[News items on Tweakers about Wordpress]( http://tweakers.net/nieuws/zoeken/?keyword=wordpress)

*[CMS]: Content Management System
