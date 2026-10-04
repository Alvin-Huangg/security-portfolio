Write notes/day-04.md: explain subdomain takeover in five sentences.

A subdomain takeover is when someone else gains control of what shows up on one of your subdomains, because your DNS still points it at a service you no longer use.

How it happens

You build a project and host it on some platform, say at alvin-blog.someplatform.com.
You add a DNS record so it looks like part of your site: blog.alvinxi.xyz is a CNAME pointing to alvin-blog.someplatform.com.
Months later you delete the project on the platform, but forget to delete the DNS record.
The name alvin-blog is now free on that platform. An attacker signs up and claims it.
Your DNS record still points there, so anyone visiting blog.alvinxi.xyz now sees the attacker's content, under your domain name.

