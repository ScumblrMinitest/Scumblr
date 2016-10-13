![Scumblr](http://i.imgur.com/iFgqbrB.png)
# Scumblr

[![Join the chat at https://gitter.im/Netflix/Scumblr](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/Netflix/Scumblr?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

## What is Scumblr 2?
Scumblr is a web application that allows performing periodic syncs of data sources (such as Github repositories and URLs) and performing analysis (such as static analysis, dynamic checks, and metadata collection) on the identified results. Scumblr helps you streamline proactive security through an intelligent automation framework to help you identify, track, and resolve security issues faster.  

Scumblr ships with a number of tasks to help you streamline security automation including:

### Sync Tasks
* **Github** - Sync results from github Repositories
* **Route53 DNS** - Sync FQDNs from Route53 DNS
* **Manual Result Upload** - Specify a new line delimited list of results you'd like to sync into Scumblr

### Security Tasks
* **Github Search** - Search Github for secrets, anti-patterns, and vulnerabilities in your repositories
* **Curl** - Execute curl commands to identify vulnerabilities or issues against Scumblr results
* **Bandit** - Perform static code analysis against Python projects
* **Brakeman** - Perform static code analysis against Ruby on Rails projects.   

### Search Tasks (legacy)
* **Google**
* **Facebook**
* **Twitter**
* **iTunes Store**
* **Certificate Transparency**
* **Ebay**
* **Google Play**
* **Reddit**
* **RSS Feeds (useful for full disclosure searches)**
* **YouTube**

Scumblr also provides a number of novel features that streamline security automation including: 

* Tracking, ticketing, regression monitoring, and auto-remediation of security vulnerabilities
* Metadata storage in results to allow for advanced result filtering
* Customizable views and sorting of results and tasks to get you to the important details faster
* Saveable result filters that can be shared with collegues 
* Event model for auditing changes to results so you can keep an eye on what is happening
* Email subscriptions for specific results or tasks you care about (such as monitoring when a security task finds a new vulnerablity)
* Advanced asynchronous task scheduling to allow for task chaining and task batching

Scumblr uses the [Workflowable gem](https://github.com/Netflix/Workflowable) to allow setting up flexible workflows for different types of results.

## How do I use Scumblr?

Scumblr is a web application based on Ruby on Rails. In order to get started, you'll need to setup / deploy a Scumblr environment and configure it to search and analyze the things you care about. Setup information is described in great detail on the [Wiki](https://github.com/Netflix/Scumblr2/wiki).

You'll optionally want to setup and configure workflows so that you can track the status of identified results through your triage process.

## What can Scumblr look for and analyze?

Just about anything! Scumblr searches utilize plugins called *Tasks*. Each Task knows how to perform a search or sync via a certain site or API (Github, Route53, Google, Pastebin, Twitter, etc.).  Tasks can be configured from within Scumblr based on the options available by the Task. What are some things you might want to look for or analyze? How about:

* Your organization's public or private github repositories
* When new FQDNS are created in your organization's DNS
* Detection of anti-patterns in source code
* Dynamic checks against running web servers for security issues
* Static code analysis across a large number of repositories using Brakeman or Bandit
* Get an alert on full disclosure security reports on vulnerabilities in your team's version of Apache

These are just a few examples of things that you may want to keep an eye on!

# Scumblr found stuff, now what?

Scumblr provides a handy vulnerablity object you can use to monitor a particular result security issues.  You can also create Status fields to associate with results, allowing you to track the state of a result or it's remediation over time.  

You can create simple or complex workflows to be used along with your results. This can be as simple as marking results as "Reviewed" once they've been looked at, or much more complex involving multiple steps with automated actions occurring during the process.

# Sounds great! How do I get started?

Take a look at the [wiki](https://github.com/Netflix/Scumblr/wiki) for detailed instructions on setup, configuration, and use!

## Release History ##

**Version 2.0** - "Dirty Laundry" - *October 12th, 2016*

This is a major release that addresses a number of bugs and adds many new features

* Refactored to be a more generic system for tracking assets and running security checks
* New task types have been created: Security Tasks, Sync Tasks, Maintenance Tasks
* New integrations for a better understanding of your environment including Github code searching, static analyzers, and dynamic checks
* New features for tracking results, searching and sorting
* New Event model for security relevant changes, error tracking, and audit purposes
* Metadata storage in results to allow for advanced result filtering
* Customizable views
* Tracking, ticketing, regression monitoring, and auto-remediation of security vulnerabilities
* Numerous bug fixes

**Version 1.0** - "Initial Release" - *August 21st, 2014*

## Contributing ##
Pull requests welcome!  See the [Contributing](https://github.com/Netflix/Scumblr2/CONTRIBUTING.md) doc for details.
