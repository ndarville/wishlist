Wishlist
========
It used to be that I could just press a button in my browser, and a link would be added to my Pinterest board of wishes. Now, Pinterest track their users across the Web, and you can't give your friends and family a shareable link that doesn't require them to register a user on Pinterest.

With Wishlist, you can create your **own** well-designed overview of your wishes with eminently readable text and mobile support. Independent on the whims, motives, and business models of other websites.

Of course, this is a wishlist mainly in name; if you want to create a list of charities or causes for people to support, you go right ahead and realize that project. In keeping with the spirit of these times, Wishlist also has built-in support for adding a list of charities people can donate to in your name in place of or in tandem with other regular wishes on your list.

The emphasis of the wishlist design is that the text is big, filled with images to explain the product, and last but not least, an ordering based on price ranges, which is the main deciding factor for a purchase.

The site will be available at `github_username.github.io`.

If you know your way around Jekyll, GitHub, or static pages, you’ll also know how to host this elsewhere.

The project uses `robots.txt` to deter search engine indexing by default.

How-To
------
1. Create a GitHub user, if you don’t already have one. Here is the [registration page][].

    Make **sure** to choose a username that easily identifies you, eg

    * `firstname|lastname`
    * `firstnameInitial|lastname`

    as the username will be a part of the website URL.

2. Go to your [e-mail settings][] and make sure you’ve checked the box “Keep my email address private”.
3. [Create a repo][] named `{{ github_username }}.github.io` on GitHub.
4. Import the required code by going to

        https://import.github.com/{{ github_username }}/{{ github_username }}.github.io/import

    and entering

        https://github.com/ndarville/wishlist

5. Update `wishes.yml`, when you create new work you want to share.

    You can do this with Git or the browser interface at

        https://github.com/{{ github_username }}/{{ github_username }}.github.io/edit/master/_data/wishes.yml

6. There’s also an optional `/_data/charities.yml` you can edit, if you want to encourage friends and families to donate to a charity in your name instead.

    This is enabled by default and uses the American Civil Liberties Union as an example.

    To disable charities for your wishlist, set the field `enable_charities` in `index.markdown` from `true` to `false`.

Congrats on your new site!

If you’ve received one of your wishes, you can either delete them or mark them as `bought: true`. If you do the latter, it will show up on the `/bought` of your site. You can also use `hidden: true`, if you want the wish not to be displayed anywhere for the time being.

**NB:** Remember to link to the *HTTPS* version of you website, as GitHub Pages does not redirect from HTTP automatically. (If you forget or don’t understand what this means, it’s not the end of the world.)

Can I use a custom domain name?
-------------------------------
[You sure can][custom-github-pages], but this is for what you might call technical people.

I use it myself for [some of my projects][hafnia-times].

I can’t get it to work :(
-------------------------
You’re welcome to contact me about this as well. We’ll figure it out.

Will my site automatically be updated with new features?
--------------------------------------------------------
Nope. You’ll basically have to follow the so-called [commit history][] for updates that sound important to you and copy-paste them yourself.

It is unlikely that there’ll be significant updates, but it is possible that changes will be made to `index.markdown` or `_layouts/default.html`.

Should this happen, and you *really* want to update your site, I recommend you just copy-paste the code to your current files and save the changes. I *do not* recommend you delete your site, re-create it, and then re-import this repo, as you will lose the information your entered in `data/wishes.yml` and `_config.yml`.

For this reason, it never hurts to have a backup of `wishes.yml` somewhere else, should you manage to pull what I just described.

Never underestimate your ability to do something obscenely dumb, especially when the hour’s late or alcohol is involved.

Related projects
----------------
* [Workfolio][]

Credits
-------
* [Flat UI][], the CSS framework for this project

TODO
----
* RSS?
* Capitalization of each word in a link name
* Remove price range if all wishes are hidden or bought


[registration page]: https://github.com/join
[e-mail settings]: https://github.com/settings/emails
[create a repo]: https://github.com/new
[custom-github-pages]: https://help.github.com/articles/setting-up-a-custom-domain-with-github-pages/
[hafnia-times]: https://github.com/hafniatimes/hafniatimes.github.io
[commit history]: https://github.com/ndarville/wishlist/commits/master
[workfolio]: https://github.com/ndarville/workfolio
[flat ui]: https://designmodo.github.io/Flat-UI/
