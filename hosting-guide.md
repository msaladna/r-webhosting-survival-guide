# Hosting types

Hosting comes in three basic formats with the distinction coming down to isolation. Shared runs multiple accounts on a single OS whereas VPS runs single accounts on multiple OSes on a single server and dedicated runs a single account on a single OS on a single server.

## Shared hosting

Shared hosting is the original mainstream way of hosting web sites. Although multiple accounts will exist on a single OS, security has improved considerably over the last 20 years. Depending upon technology (e.g. [CloudLinux](https://www.cloudlinux.com/), [Virtuozzo](https://www.virtuozzo.com/), [Docker](https://www.docker.com/)) shared hosting can be enhanced to provide OS-level segregation that isolates accounts from one another affording some protection from curious neighbors.

Shared hosting is second oldest only to dedicated servers and with age comes a wide range of implementations. Shared hosting with isolation is sometimes referred to as "cloud" hosting because of stigmatization of "shared" over the decades.

### Expectations

Shared hosting provides limited managed hosting. A good shared hosting platform will take care of:

* Control panel to manage user accounts (such as Plesk or cPanel)
* OS security updates
* Monitoring services (email, web, hardware)
* Providing a system to automatically update popular web applications (WordPress, Drupal, et cetera)
* Platform migrations when the OS reaches end-of-life (every 5-10 years)
* Ensuring email is deliverable and remediating deliverability problems
* Reducing email spam that arrives in user mailboxes. Only a handful of false negatives (email not marked as "spam") should arrive per day

### Pros

* Provides basic management services, including tools to build a web site and manage email

### Cons

* Limited growth options available
* Hardware can be sorely lacking as the requirements to run a shared hosting business are minimal 
* Cannot run services or install software beyond what is provided

### Considerations

Avoid hosts that advertise unlimited storage. These providers have restrictions in fine print that restrict how you use your storage and how much you can actually use (called "inode restrictions").

[EIG brands](https://en.wikipedia.org/wiki/Endurance_International_Group#Subsidiary_brands) and GoDaddy are also a big no-no as both have a habit of maximizing profit at the expense of customer satisfaction. Examples of this include EIG's [SiteLock service](https://www.whitefirdesign.com/blog/2017/05/16/a-nexus-of-insecurity-between-eig-sitelock-and-mojo-marketplace/) that exists solely to disinfect compromised sites or GoDaddy's [removal of ticketing](https://wptavern.com/godaddy-removes-ticketing-and-email-support-in-favor-of-phone-and-live-chat) in favor of live chat. 

A properly managed shared hosting company should provide automatic updates for software, especially Wordpress, and provide some malware protection whether it be a firewall or permission restrictions. Lack of permission restrictions, that is to say running everything under a single user, is exactly how the [Panama Papers hack](https://www.wordfence.com/blog/2016/04/panama-papers-wordpress-email-connection/) happened... These features *should* be standard as providing such improves server security, reduces administration costs, and increases customer satisfaction for these companies.

GoDaddy's decision to remove ticketing is even worse, it's an iron fist in a velvet glove that was spun as a decision to improve customer satisfaction by offering real-time support. In reality, support queues are dependent upon the number of customers seeking support and GoDaddy no longer has to hire additional support personnel to meet support demand. GoDaddy wins and customers lose.

General consensus is to avoid both EIG and GoDaddy brands.

## VPS hosting

VPS is a relatively new form of hosting that relies on virtualization capabilities of modern CPUs. VPS has also made running a server more affordable; before VPS the only way to have total control over your server was to buy a dedicated server. 

There is a growing trend that recommends VPS for all forms of hosting, even those who aren't familiar with how to manage a server and this is a dangerous trend. I will touch on this in the next section. Unless you have requisite sysadmin skills or can put in at least 10 hours a week to learn how to manage a server, *do not* jump to VPS

### Pros

* Inexpensive way to learn to manage a server
* VPS provides some opportunity to scale up as hardware demands increase (memory, CPU, storage)
* Encourages horizontal architecture for complex web sites ("cattle, not pets" mantra)
* Billing is prorated per minute

### Cons

* True hardware requirements are hidden. A VPS can be split unlimited ways and configured many ways. For example a VPS can advertise 4 CPUs (virtual CPUs) and be connected to 1 CPU in the hypervisor (logical CPU) thus negating the benefits of 4 CPUs
* VPS is unmanaged, when you break it - you fix it. System administration skill is required
* Performance deteriorates as servers age and accumulate cruft from bad tenants

### Considerations

In the VPS world there are three established providers, [Digital Ocean](https://www.digitalocean.com), [Linode](https://linode.com), and [Vultr](https://vultr.com) (owned by [Choopa](https://www.choopa.com/)). VPS is *unmanaged*. Unmanaged does not provide support for things you do with your server, but it does provide hardware monitoring and repair if something is defective physically on the server (hard drive dies, motherboard blows a capacitor, etc). In its simplest sense, VPS is [pure competition](https://www.investopedia.com/terms/p/perfectcompetition.asp) and the product being sold is a commodity, so stick with one of the three and you'll be fine.

Like shared hosting, hardware is still shared among multiple neighbors. Noisy neighbors can therefore consume your resources and impact your performance. Discerning whether you're on a congested server is discussed in the following section. Be forewarned, it's difficult to determine.

## Dedicated hosting

Dedicated hosting is the original hosting model - buy a server, use a server.

### Pros

* Hardware is dedicated 100% to you
* Most provide some management terminal (called OOB) that allows you to connect to the server on startup

### Cons

* As a single customer, a hardware failure will be deprioritized in favor of servers with many tenants. Losing a single customer over a failed server near as bad as losing several hundred
* Hardware can have hundreds of hours on it thus increasing the likelihood of failure
* Server management is the responsibility of the customer unless separate management services are purchased

### Considerations

Having a keen eye and patience can pay off in finding an excellent deal as data centers rotate out fleets of decommissioned servers. Renting VPS is like renting an apartment in a complex; even if 50% of the apartments are rented the apartment complex breaks even. No matter how many tenants reside, it still takes up the same space. Renting a dedicated server is like renting a home. It's occupying space and there can only be 1 home occupying a parcel of land. This puts companies under greater pressure to make concessions to rent out the server.

# Hybrid hosting types

Hybrid hosting is hosting that sits on top of one of the three hosting models mentioned above.

## Reseller hosting
Reseller hosting piggybacks shared hosting and allows you to create multiple shared hosting accounts. It affords all of the same benefits of shared hosting and gives you the flexibility to add/remove hosting accounts independent of one another.

Reseller is ideal for web designers that don't want to manage a server.

### Pros

* Same benefits as *shared hosting*
* Allows for multiple accounts to exist independent of one another

### Cons

* Same downsides as *shared hosting*

## PaaS hosting

Platform-as-a-Service is a hosting model that leverages proprietary platforms to manage various aspects of hosting. For example, [Heroku](https://www.heroku.com/) is a service that provides command-line tools to create complex software stacks without administering the server or ensuring service availability.

### Pros

* Decouples server management from development - focus on software instead of server management
* Deployment is API-driven - use commands from desktop to create components or send code to production

### Cons

* Proprietary platforms conceal processes that can misrepresent real performance. [Heroku's Ugly Secret](https://genius.com/James-somers-herokus-ugly-secret-annotated) (Genius) 
* More expensive than other forms of hosting

## IaaS hosting

Infrastructure-as-a-Service is a robust variation of PaaS. Instead of focusing on one aspect, running code, IaaS provides a variety of services that work together. IaaS examples include [Google Compute Engine](https://cloud.google.com) and [AWS](https://aws.amazon.com). These providers span a gamut of services from anycast DNS, data storage, content delivery network, monitoring, load balancing, database instances, and so on.

### Pros

* Allows for very elaborate setups
* Expenses shift from capital expense to operational

### Cons

* More expensive than on-premises hosting
* Hardware fails. There is no guarantee of data integrity and guidelines recommend building to sustain loss of an individual node

# Understanding hardware

Hardware is a great topic that could be discussed in a book its own, but for simplicity let's break down the 4 main components that affect a website in importance:

## CPU

Analogy: **water wheel**

CPU is the brains of the operation. Not only does it allow e

## Memory

Analogy: **storage closet**

When the CPU is done computing information it's stored in memory if storage permits. Storing and retrieving information is very fast, but there's only so much memory available.

## Disk

Analogy: **storage unit down the road**

When a server runs out of memory to store information in or that information is old, it gets sent to disk; this process is called [paging](https://en.wikipedia.org/wiki/Paging). 

## Network

Analogy: **highway**



# Running a server

Running a server isn't an easy feat, in fact it is still a [profession](https://www.glassdoor.com/Salaries/systems-administrator-salary-SRCH_KO0,21.htm) that requires significant learning to achieve proficiency. Imagine for a moment you love glamping: take the Jeep to a public campground, you've got public showers, running water, a hookup for electricity, and a store a few miles away - life is great. This is shared hosting, everything is provided for you. 

Managing a server is making your next trip to [Denali wilderness](https://www.nps.gov/dena/learn/nature/wilderness.htm) where there's only primitive camping and grizzly bears, lots of grizzly bears. It's not a matter of if you'll get eaten, but *when*. This is running your own server. It can be an extremely rewarding experience, but requires experience to understand. The following sections discuss problems I've observed from recommendations mostly in [r/webhosting](https://reddit.com/r/webhosting).

## Bit rot

[Bit rot](https://en.wikipedia.org/wiki/Software_rot) is the gradual decay of code either through technical obsolescence. Everything eventually fails, so enabling automatic system updates are one key part of the puzzle to ensure a server runs reliably. Bit rot

## Brute-force and recidivism



## Mail server

Three words: **don't do it**. 

Mail is a persnickety beast that requires very careful configuration. Having at least 2 IP addresses is crucial because not all mail providers offer means to remove your server from a blacklist if it is compromised. FBL ("feedback loop") participation is key to monitoring the mail that leaves your server and act accordingly. Sometimes when a spam is reported through FBL, the server is already blacklisted for 48-72 hours thus interrupting the flow of mail (this is where having a second IP is crucial). FBL publishers have differing rules, some require you to be the ARIN contact for the IP subnet; you won't have this unless you manage an entire IP block and your hosting provider is unlikely to bestow the privilege.

Your best bet is to host email with a third-party provider such as Outlook, GMail, [Zoho](https://www.zoho.com/mail/?), or [MXRoute](https://mxroute.com). You can even use GMail to [relay mail](https://www.linode.com/docs/email/postfix/configure-postfix-to-send-mail-using-gmail-and-google-apps-on-debian-or-ubuntu/) from your server using Postfix. Postfix is a popular mail server available on all Linux distributions and one I am very familiar with.

---

Now let's ignore this sage advice and host a mail server because opinion is overrated or because you're a masochist or you're interested in becoming a system administrator. 

Here are some basic guidelines I recommend. These are tailored to [Postfix](http://www.postfix.org) where appropriate.

### Always require SMTP authentication, including from local TCP connections

TCP is anonymous. When a user opens a connection over `127.0.0.1:25` (SMTP port) the kernel has no idea who opened it but just that a connection is opened and the initiator is also 127.0.0.1. This means if a malicious agent gains the ability to execute arbitrary code on your server, then you have no idea where it's coming from. This sucks for hopefully clear reasons.

Some malware takes advantage of this peculiarity, such as [StealRat](https://gist.github.com/elektret/6881671). 

### Block outbound SMTP access for non-mail user

Going back to getting compromised

```bash
iptables -A OUTPUT -d 127.0.0.1 -p tcp -m tcp --dport 25 -j ACCEPT
iptables -A OUTPUT -p tcp -m tcp --dport 25 -m owner --gid-owner mail -j ACCEPT
iptables -A OUTPUT -p tcp -m tcp --dport 25 -m owner --gid-owner mailman -j ACCEPT
iptables -A OUTPUT -p tcp -m tcp --dport 25 -m owner --uid-owner root -j ACCEPT
iptables -A OUTPUT -p tcp -m tcp --dport 25 -j REJECT --reject-with icmp-port-unreachable
```



### Enforce rate-limits



### Jumpstart spam filtering with Enron corpus

### Enable DKIM, DMARC, and SPF