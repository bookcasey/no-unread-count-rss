# No unread count RSS

Scrolls down to last seen article instead.

Minimalist RSS feed inspired by [Silvio Rizzi's yet to be released Reeder](https://gloria.social/@rizzi/111856959119832404)

[Try it out](https://bookcasey.github.io/no-unread-count-rss/)

## Why?

Unread counts make RSS feel like an email inbox, which feels like work.

Feeds that don't keep track of anything (YouTube subscriptions, [Bubo](https://github.com/georgemandis/bubo-rss), [osmosfeed](https://github.com/osmoscraft/osmosfeed)), make you remember and then scroll down to the last thing you viewed, which is tedious.

I like reading blogs on the web, so it's a feed and not a reader.

## Make your own

Fork this project and update the `feeds.json`. Modify `site` in `astro.config.mjs` to match your GitHub pages URL.

## Technical details

Static site built with Astro.js with a few lines of Vanilla client-side JS. Stores the newest article that has entered view in `LocalStorage`, on load will scroll down to that article.

Default deployment is on GitHub pages, with a GitHub Actions CRON job that updates twice daily.

## FAQ

### Can anyone see my feed if it's deployed on GitHub pages?

Yes, but your scroll position is stored locally. Fork it, host it somewhere else, and add authentication if you please.

### I'm refreshing to test it, and it's not remembering where I was!

On load it will scroll down to the most recently posted article that you have seen. If you scroll down further to older articles and then refresh, it will take you back up to that most-recently posted seen article. It would have been simpler to implement a version that just saved the scroll position, but that was not my intention.

### I don't like visited links being purple

Fork it and add `a { color: blue }` to the `style` block in `index.astro`

### Can I view feed for just one blog?

No. Go to the homepage of that blog.

