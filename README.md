# Performer
A theme for [Ghost](http://github.com/tryghost/ghost/) targeting self-promoting performers (DIY musicians).  

# Project History / Motivation
I keep a regular day job as a web developer to pay my bills, but my real passion is playing music. A few years ago I decided that I was not doing enough of my passion, and that it was time to start.  

One of the things I needed to do was get the word out to people about where and when and with who I am going to be playing. I had worked with WordPress once before and was not all that impressed or excited to use it for myself. The plugins I found were hard to style and/or just felt clunky. The blogging platforms out there didn't offer enough expandability to put in things like event calendars or web stores for selling merch.  

Ghost hit the right tone for me - own your own platform and your content. But it doesn't have a plugin system where one can go find event calendars and commerce modules. So, with my skillset and a healthy dose of punk-rock DIY attitude, I set out to create this theme to fill a few gaps:  

- Treat events like a blog post. Allow discussion, some editorial (i.e. making a thank you note to the host)
- SEO on every event (if it's easy for people to find you, they will find you!)

Ghost's post system does most of the work. All that's really needed is to detect when a post is an event, and then render it with a custom handlebars template.  

The really exciting thing about Ghost is that posts made with it conform to [Open Graph](https://ogp.me), making [integration with social media](https://ghost.org/integrations/facebook/) quite easy. The Event Posts I make in Ghost go downstream to social platforms with a link back to my site. Ownership of my content is clear.  

# Technical Help
- Support is not being offered at this time because this is just for my private use. Maybe this project will gain some popularity; we'll deal with it later if that happens.  
- See the [upstream fork's README.md file](https://github.com/TryGhost/Casper).
- Read up on [Handlebars](http://handlebarsjs.com/).

# Developer Notes

## Working with a local copy of Ghost
1. Follow instructions to set up a Ghost dev environment [here](https://ghost.org/docs/install/local/). I named mine `ghost-local`.
1. Clone this repository to a separate location. 
1. `ghost stop` if it is running.
1. In the `ghost-local` navigate to `content/themes/` and create a symlink to the root of this repository.
1. `ghost start`
1. Open the admin panel via localhost and set the theme to `performer` (it should show up as an option now).
1. Get to work!

## Working in the Casper fork
The `master` branch is a copy of the upstream fork. Main changes are done in `master-fork` branch.  

It is desired to pull in changes from the upstream forked repository from time to time. For that reason, the `master` branch is left in-tact and should never be pushed to. Instead use the `master-fork` branch for working commits, and rebase it on top of `master` as needed.  Do `--ff-only` merges in this case.  

Set up a git remote of the master with this command:

    git remote add upstream git@github.com:TryGhost/Casper.git

Pull in updates, update master:  

    git fetch -p origin/upstream
    git checkout master
    git merge origin/upstream

Rebase working branch on top of updated master:  

    git checkout master-fork
    git rebase origin/master

It's done this way to help keep my changes in a separate timeline from the main development, so that the theme package can easily take updates.  

# Copyright & License
Original work Copyright (c) 2013-2020 Ghost Foundation - Released under the [MIT license](LICENSE).  

This work is a derivative of the Original work. At this time it is intended only for private use.  

