# Chris Long — LinkedIn Posts

Collected: 2026-07-09

---

## Post 1 — 5 Hours Ago
URL: https://www.linkedin.com/posts/chris-long-marketing_big-seo-news-google-is-now-showing-ai-overviews-activity-7480667040702242816-Z_QO
Attachment: Image

Big SEO News: Google is now showing AI Overviews for brand queries.
Expect declines in clicks/CTR for brand searches + more users going to
AI Mode:

Author's Note: To get tips like this straight to your inbox, check out
the newsletter in my bio.

Well this is something I just started seeing today across a couple of
brand searches. Others such as Ryan
Jones have also seen it as well.
Google is showing AIOs across brand searches directly.

This has some pretty major implications:

1. Expect branded clicks to start decreasing when it rolls out entirely.
This is similar to what we've seen from AIOs on non-brand terms. I
wouldn't expect it to be AS harsh as non-brand though.

2. Now AI has more control over your brand. AI is going to push your
brand's narrative directly in the search results before users even
interact with your site.

3. Now other sources of information are influencing the results. I'm
seeing Google pull from LinkedIn, news articles and sources outside of
the home page.

4. This creates a major entrance point for AI Mode. Now Google is
pushing users into the LLM even across searches for your brand. This
creates a lot of opportunity for users to enter in the platform and
start asking questions without visiting the site directly.

**Attached images:** image25.jpeg (saved in `images/chris-long/`)

---

## Post 2 — 9 Hours Ago
URL: https://www.linkedin.com/posts/chris-long-marketing_awesome-seo-tip-common-crawl-is-the-biggest-activity-7480606799860211712-M-oT
Attachment: Image

Awesome SEO Tip: Common Crawl is the BIGGEST source of training data for
LLMs. Here's how to audit if your site is in the training data in just
5 minutes:

Author's Note: To get tips like this straight to your inbox, check out
the newsletter in my bio.

So this is a pretty sweet tip that Jason
Melman just
shared at our internal
Nectiv meeting
yesterday. Common Crawl recently released "The AI
Visibility Audit" guide that gives some really solid information about
getting your site included on Common Crawl's dataset.

For those that don't know, Common Crawl is probably the biggest source
of LLM training data. It's a massive public resource that most frontier
models have almost certainly used to train their knowledge bases.

Well in the article, they actually showcase how you can use the command
line to check whether your site is included in the latest version of
Common Crawl. It sounds difficult but it's pretty easy to do. I'll
give an example of how to check it using DocuSign.

1. Open up your Command Line on your device
2. Define the Domain: DOMAIN="docusign(dot)com"
3. Test if CCBot can access the site: curl -A "CCBot/2.0" -I
"https://$DOMAIN/"
4. Check whether the domain is in the latest version of Common Crawl:
curl
"https://index(dot)commoncrawl(dot)org/CC-MAIN-2026-21-index?url=$DOMAIN/*&output=json"
| head

You'll then get a response to see if your site is included in the
latest version. If you see your site get included in the response,
you'll confirm whether or not it's getting picked up in Common Crawl.
You'll then have confirmation whether or not LLMs are able to use your
site in the training data.

**Attached images:** image26.jpeg (saved in `images/chris-long/`)

---

## Post 3 — 1 Day Ago
URL: https://www.linkedin.com/posts/chris-long-marketing_big-seo-news-social-media-data-is-coming-activity-7480270805285830656-VaSN
Attachment: Image

Big SEO News: Social media data is coming to Search Console. "Platform
Properties" lets you see click, impression + search queries from social
profiles:

Author's Note: To get my top posts right to your inbox, check out the
newsletter in my bio.

This is a pretty big update from Search Console. They announced that
they're adding "Platform Properties" reporting. You'll be able to
connect your key social profiles and be able to see key data such as
click, impressions + search queries. Right now the available platforms
are  Instagram, TikTok, X, and YouTube.

Google has bee doubling down on USC showing up in the search results.
Now they're integrating more reporting too. More evidence that a
comprehensive strategy needs to take the social ecosystem into account.
Google is going to continue to prioritize it.

**Attached images:** image12.jpeg (saved in `images/chris-long/`)

---

## Post 4 — 1 Day Ago
URL: https://www.linkedin.com/posts/chris-long-marketing_technical-seo-article-how-to-optimize-the-activity-7480235018649427968-nU05
Attachment: Image

Technical SEO article: How to optimize the Accessibility Tree for AI
agents. This covers semantic HTML, visualizing hierarchy, spying on
competitors + more:

Author's Note: To get my top posts right to your inbox, check out the
newsletter in my bio.

This was an awesome read this morning from John
McAlpin. Earlier Google
has reference Accessibility Trees as "high fidelity maps" for AI
agents. Well this article gives actionable advice on how to actually
optimize you Accessibility Trees for AI agents.

1. Use Semantic HTML over Generic HTML: This is a big one. If your site
is using generic tags like <div> or <span> to identify key elements,
AI agents won't know what to do. Instead, you need leverage tags such
as <button>, <form>, <select> to better showcase to AI agents what
the action to be taken is.

2. Identifying Hidden JS Content: Many sites load different content
after different interactions are performed on the page. You can use the
Accessibility Tree to audit this. For instance, you could test
interacting with different FAQ buttons to observe what information AI
agents would be getting when selected.

3. Hierarchy Validation: With all of the visuals and extra components
stripped away, Accessibility Trees give you a clean look into the
structural hierarchy of a page. You'll be able to easily visualize how
your headings + content are all nested together.

4. Competitive Analysis: This is a really unique one. John
McAlpin recommends finding
high performing competitors (getting cited, AIOs) and then extracting
the Accessibility Trees of their key templates. That can give you
insights as to how they're structuring things in order to be
successful.

**Attached images:** image27.jpeg (saved in `images/chris-long/`)

---

## Post 5 — 2 Days Ago
URL: https://www.linkedin.com/posts/chris-long-marketing_man-this-is-why-im-so-excited-about-proprietary-activity-7479946017472294912-g8w-
Attachment: Image

Man, this is why I'm so excited about proprietary research for
SEO/AEO.
LLMs are 3.3x more likely to cite content that utilizes original data:

Author's Note: To get my top posts right to your inbox, check out the
newsletter in my bio!

This was great research by Kevin
Indig + the team at
Gauge. They analyzed
around 1K citations from about a 300 page set. They looked across seven
different verticals including HR tech, crypto, financing, SaaS,
Education.

When looking at the pages, they only qualified 8 of the 301 pages as
"original research" - just 2.7%. However, when looking at how
frequently those pages were cited, they significantly over-performed.

They actually actually achieved a 8.4% citation volume with an average
of 11.3 pages getting cited. Everything else only had an average of 3.4
pages. This means that original research had a 3.3x better chance of
getting cited by LLMs.

In the article, he actually dove deeper into specific examples. He
looked at Fivetran's
"Cloud Data Warehouse Benchmark" report and found it was getting cited
in just below half of the instances. In the article, they compare the
Cost/Hour of major data warehouses against different tasks. Even though
it's from 2022 - it still get cited frequently.

Super interesting research. Also the Growth
Memo is a must read if
you haven't subscribed to it already.

**Attached images:** image28.jpeg (saved in `images/chris-long/`)

---

