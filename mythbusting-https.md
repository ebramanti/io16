# Mythbusting HTTPS: Squashing security’s urban legends

## Journey begins in 2010
- Deep sleep, wake up in 2016
- All the things you missed: web notifications, add to homescreen, access to accelerometer/sensors
- Lots of responsibility
  * Geolocation - website knows where you are
  * ISPs injecting stuff into websites
- You expect web to protect this data

## HTTPS is the answer
- Green Lock
  * so ubiquitous that it is expected for any site
- What does it mean?
  * Identity - to whom are you talking?
  * Confidentiality - who can read your data?
  * Integrity - who can modify your data?
- What do you think it means?
  * $$$ - extra cost
  * Performance - better site

## Stories about HTTPS
### My site's not important enough for HTTPS.
- Alice runs an online travel guide
- No security, no sensitive content
- No need for HTTPS?	
- One day, person says website is slow and sluggish
- Goes over to person's house, checks what is going on
- Ads are being injected into Alice's site.
- Alice's friend trusts Alice's site, expects ads to not be malware
- New feature with geolocation written by Alice, needs HTTPS to be secure so geolocation is not leaked
- HTTPS is no longer for especially important or sensitive sites.

### HTTPS will slow down my site.
- Bob, data-driven, e-commerce
- Yell.com, switched to HTTPS, saw a performance impact
- Google in 2010 migrated to HTTPS with negligent performance impact (<1%)
- What can you do to lower performance impact?
  * HTTP 301 to https is an impact
  * TLS requires a handshake which requires two round trips to the server
  * After that, then the HTTPS request can be sent
- What can we do to optimize?
   * HTTP Strict Transport Security: always should be accessed over HTTPS
   * TLS False Start: allows you to stuff HTTPS request into the second round of handshake in TLS
   * TLS Session resumption: allows you to avoid a roundtrip with a session ID after the initial request
- HTTP/2: next version unlocks massive performance wins
  * HTTP 1.0: requests+responses are sent and received in order
  * HTTP/2 multiplexing: use the same connection for multiple requests and responses at once
  * HTTP/2 server push: proactively push resources that the client will need before they are requested
  * Browsers only support HTTP/2 over HTTPS.
  * This provides an incentive to move to HTTPS
- Yell.com, negative performance impacts were load-balancing related, HTTP/2 will improve TLS negotiation
- Weather.com, ~250ms saved in HTTP/2 request

### Aren't there a bunch of new attacks on HTTPS?
- There have been SSL/TLS vulnerabilities (BEAST, CRIME, BREACH, Heartbleed, FREAK, DROWN)
- HTTPS is like a lifejacket with a few defects, HTTP is like no lifejacket at all
- Use tools and support out there to keep config up to date
- Tool example: [SSLLabs](ssllabs.com)
- For high quality HTTPS, keep servers/configuration up-to-date.

### HTTPS will cost too much money.
- Does HTTPS cost $?
  * Certificates
  * Search Ranking
- Certificates
  * You buy a certificate from a certificate authority (CA).
  * How much do they cost? See SSLMate, $15, and Let's Encrypt, free
- Search Ranking
  * Search engines might get confused, might lose search ranking
  * Google has best practices for moving your site: 301 Redirects, serve canonical link element, see guidance from Google
  * Search ranking fluctuation should be minimal

### I can move my site to HTTPS, but what about the 3rd parties I depend on?
- Ads
  * Will ads be available over HTTPS?
  * For most users, AdSense ad requests are always served over HTTPS.
  * Exception: users who are in countries who block HTTPS traffic.
  * Industry-wide trend
  * 80% of ad delivery networks support HTTPS - IAB
  * Serving ads over HTTPS shouldn't be a blocker
- Referrers
  * When a user clicks a link on site, referrer put in header
  * Could be used for analytics/making money
  * When you move site to HTTPS, when link follows HTTP site, it will strip out referrer header
  * Won't leak in plain-text
  * Problem for people who link to HTTP partners
  * Referrer Policy allows you to loosen restrictions on the referrer header
- Mixed Content
  * Non-secure subresource can compromise security of HTTPS website
  * Examples: Script, iFrame
  * Browsers block it
  * In the case of images, this will knock out the "Green Lock"
  * Content Security Policy is the solution
  * Allows you to specify what's supposed to be served over HTTPS
  * You can use [report-uri.io](report-uri.io) to collect Content Security Policy reports to see what requests are happening.
  * Chrome DevTools Security Panel can be used to see what the mixed content is.
  * 3rd party providers must support HTTPS in order to move site over.
  * Once they do, new tools and support in the ecosystem can help you migrate.
## Moral of the Story
- HTTPS used to be hard, slow and expensive.
- In 2016, HTTPS is faster, easier and cheaper
- A requirement for progressive web apps

   



