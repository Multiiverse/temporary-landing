<!-- markdownlint-disable MD025 -->
# What is Multiiverse?

Multiiverse is a service that allows you to post to multiple Miiverse clones as if they were all one place. It has two purposes:

* To present posts to Multiiverse users, so they can post to your clone from the Wii U, 3DS, or the Multiiverse website.
* To archive posts on Miiverse clones, so the history of your clone can be preserved.

# For users

## Confirming a Multiiverse bot account

Multiiverse operates a few IDs across different clones and networks to help you prove you are who you say you are, even if you don't want to give Multiiverse full access to your account. (When Multiiverse launches, a list will be provided.)

## Do not allow others to login to your Multiiverse account

Multiiverse, by necessity, collects some sensitive information about your console during the linking process in order to function. (When Multiiverse launches, a list will be provided.)

Since a Nintendo Network ID can only be connected to one Wii U and 3DS console at a time, Multiiverse is required to impersonate your console to work with certain endpoints. Therefore, if you share your Multiiverse account with someone else, they may be able to post as you *as if you were using your console*. Instead, each user using Multiiverse should create their own account.

We offer two-factor authentication through an authenticator app to help limit the impact of account sharing. In general, you should protect your serial number and device certificate, even outside of Multiiverse.

## Be careful what you post

Please remember to follow the Code of Conduct for to the clones you post on, where possible. Multiiverse itself also has a Code of Conduct that determines what posts will be visible through our public index.

Additionally, the Miiverse Clonapedia has access to our post archives for their historical and cultural research. When you post, you should expect your posts may be used for this research.

## Controlling archival and indexing permissions

If you are reading this section to opt out of indexing, we hope you will reconsider. We provide Multiiverse as a public service to help preserve clone history.

If you are facing ongoing harassment, we advise you to do all of the following, in this order:

1. Contact your local law enforcement if you know the person harassing you in real life, or otherwise believe they may have personal information such as your physical home address.
2. Block the offending user(s) on the clones you use.
3. Block the offending user(s) through Multiiverse.
4. Contact the moderators of the clone you use if possible. We provide contact links for each clone to help facilitate this.
5. [Contact us](/contact). We are willing to assist you with steps 1-4, as well as work to help mitigate the harassment you are receiving where possible.

We process the relevant personal data here per exemptions to the UK GDPR and DPA for a) [archiving purposes in the public interest](https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/exemptions/a-guide-to-the-data-protection-exemptions/#ex18), and b) [sharing archived posts with Miiverse Clonapedia for historical research purposes](https://ico.org.uk/for-organisations/uk-gdpr-guidance-and-resources/exemptions/a-guide-to-the-data-protection-exemptions/#ex17).

With that said, we still attempt to make accommodations. Our default policy is that if all of the following apply, a post you make is only preserved for two years after a clone's shutdown:

* You are not an active staff member of the network/clone you originally posted on.
* At the time of posting, you were not a staff member of the network/clone you originally posted on.
* Your account remains unbanned on the network/clone you originally posted on.
* Your post does not have more than 10 likes.
* You have not linked your account to a Multiiverse account.
* The Miiverse Clonapedia has not deemed your individual post in the public interest.

Otherwise, your post will remain preserved for as long as Multiiverse is active. Additionally, even if all of the above do apply, you can use hashtags in the description (or otherwise equivalent field, such as a profile comment) of your account to limit how Multiiverse interacts with your future posts if you're not a staff member of the network/clone you're posting on:

* If you include `#noindex`, future posts will only be *indexed* for two months from their creation date.
* If you include `#noarchive`, future posts will only be *archived* for six months from their creation date.
* If you include `#nobot` or `#nomultii`, future posts will a) only be *indexed* for two months from their creation date, and b) only be *archived* for six months from their creation date.

You may [contact us](/contact) to have your archived posts disassociated from your account without creating a Multiiverse account. If you have a Multiiverse account, you can do this yourself through your account settings. Please note that this only affects the archive, so user information will still be fetched (but not preserved) if the account still exists on the clone and the post is up.

## On using Multiiverse with Juxtaposition

Multiiverse violates Rule 8 of the [Juxtaposition Code of Conduct](https://forum.pretendo.network/t/juxtaposition-code-of-conduct/8407). Additionally, Multiiverse (by necessity) collects some sensitive information about your console in order to function. While we don't believe anyone's account or console will be banned from Juxtaposition for using Multiiverse, it is important to mention that you use this service with your Juxtaposition account at your own risk.

# For website owners

Multiiverse is a service that scrapes Miiverse clones in order to function properly.

Multiiverse identifies itself by including `MultiiverseBot/1.0` in the user agent, and by signing its request with a cryptographic signature in accordance with [Web Bot Auth](https://datatracker.ietf.org/doc/html/draft-ietf-webbotauth-httpsig-protocol). It also understands `robots.txt`, and reads/respects the following directives:

* `Robot-version`
* `Disallow`
* `Allow`
* `Content-Signal`
* `Crawl-delay`
* `Host`
* `Noindex`
* `Request-rate`
* `Visit-time`

Multiiverse will read rulesets for the following user agents:

* `*` (generic)
* `other2_0` ([generic](https://www.robotstxt.org/robots-webcrawler-mbox.txt#:~:text=Has%20anyone%20suggested,other2_0))
* `MultiiverseBot`
* `MultiiverseBot/`
* `MultiiverseBot/1.0`

We may change the below behaviors at any time, but pledge to provide 1 month of notice where possible. We will attempt to contact you directly where possible, but it is your responsibility to check and make changes as necessary.

## Behavior with `Robot-version`

`Robot-version` is either a three-part number or two-part number. If `Robot-version` is a three-part number, and the second part of `Robot-version` is odd, the ruleset will be considered experimental and will be ignored.

## Behavior with `Disallow`

By default, `Disallow` blocks all paths starting with and including the specified path.

If `Robot-version` equals `2.0.0`, then this is not the case and `Disallow` will only block the specified path. Note that this is if `Robot-version` equals `2.0.0` and not `2.0`.

To keep your directive behavior consistent across recognized `Robot-version` types, add `*` to the end of the directive.

## Behavior with `Allow`

By default, `Allow` allows all paths starting with and including the specified path.

If `Robot-version` equals `2.0.0`, then this is not the case and `Allow` will only allow the specified path. Note that this is if `Robot-version` equals `2.0.0` and not `2.0`.

To keep your directive behavior consistent across recognized `Robot-version` types, add `*` to the end of the directive.

## Behavior with `Content-Signal`

To be clear, Multiiverse does NOT use artificial intelligence, generative or otherwise. We do not use it in our code, our original art, or as part of our crawling process. We do not share our data or information with AI crawlers or scrapers, and actively attempt to block them from accessing our websites and services, even if they are "operated by a human" (e.g. agentic browsers).

Even so, we choose to respect Content-Signal in the following ways:

* We will prevent our users from interacting with users and posts if a `Content-Signal` directive set for `MultiiverseBot`, `MultiiverseBot/`, or `MultiiverseBot/1.0` has a `use` signal set to `reference` or `immediate`. In the event such a signal is not seen, we will also prevent our users from interacting with users and posts if a `Content-Signal` directive set for `*` or `other2_0` has a `use` signal set to `immediate`.
* We will prevent our users from searching for specific users and specific posts through search functionality if direct links to the posts are included in `Disallow` (patterns do not count), and the `search` content signal is set to `no` (if it exists at all).

## Behavior with `Crawl-delay`

In order to prevent misconfiguration (and facilitate the correct operation of Multiiverse services), `Crawl-delay` has a maximum value of `120`, which is 2 minutes.

## Behavior with `Host`

The current domain and the domain specifies in `Host` are both expected to have byte-for-byte identical `/robots.txt` files.

## Behavior with `Noindex`

On user-specific or post-specific paths, this directive will only be respected for users who do not have a Multiiverse account. Otherwise, the user is expected to themselves manage indexing for their own posts and accounts.

If you wish to opt out of indexing for your entire clone, please instead [contact us](/contact) and we can assist you.

## Behavior with `Request-rate`

This directive is only active if `Robot-version` is either `2.0.0` or `2.0`.

This directive is only followed for indexing and archiving independent of user action. The maximum time normalized is `1/5`.

## Behavior with `Visit-time`

This directive is only active if `Robot-version` is either `2.0.0` or `2.0`.

Please do not use `Visit-time` to attempt to stop Multiiverse from accessing your clone. Instead, [contact us](/contact) and we can assist you.

Your times should ideally be set within a timeframe of when posting is most active. In the event your directive is less than 6 hours, the end time will be extended to 6 hours after the start time.

## Behavior with `Comment`

Comments with this directive given to `*`, `other2_0`, `MultiiverseBot`, `MultiiverseBot/`, and `MultiiverseBot/1.0` are forwarded to us.
