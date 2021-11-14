# Intro To Django

## How Django Works Behind the Scenes

![](https://external-preview.redd.it/P53_07QnF2IBiXbEYCRb2LgU6moj-h6ZFCvZHFzBMtQ.png?auto=webp&s=9bbaf0e3c46d6ee7c44f6d50268eff40e3a29d89)

- **Django** is a Python-based web framework used by millions of developers and billions of consumers through popular apps like Instagram.

 It is open-source, meaning the code is available *for free on Github* and can be downloaded onto any developer’s computer and used alongside the official documentation. 
 
 However, I find that even professional Django developers have little insight into “how” Django is actually run, both technically and legally/financially, so this post is my attempt to provide a concise overview of it all.

 - Django was originally developed at the Lawrence Journal-World newspaper by Adrian Holovaty, Simon Willison, and Jacob Kaplan-Moss. The code was open-sourced in 2005 and developers immediately started making contributions to the codebase. Fourteen years later, Django remains under active development, with new major releases every nine months, minor security releases almost monthly, an official issue tracker, and robust discussion on the Django-developers Google group.


 - As with all open-source projects, the two major issues that crop up are funding and control. Let’s start with funding: why does an open-source project need funding?

It turns out that while writing code is fun and developers are generally willing to contribute their time for free to do so, there are a host of decidedly fewer fun tasks needed to maintain and sustain an open-source project. This includes handling any legal/trademark issues, triaging tickets, guiding community discussions, organizing conferences, managing releases, and so on. As a result, almost all popular open-source packages have some degree of funding involved, typically in one of three forms:

1) **Corporate** Sponsor - A group of engineers within a larger, for-profit company decides to open-source internal code. This is how React (Facebook) and Angular (Google) emerged. Typically engineers at the company are paid, in part, to work on open source though community involvement from developers outside of the core company occurs as well. While this structure has the stability of a wealthy benefactor, there can be confusion around the licensing aspects at times.

2) **Solo** - An individual developer initially creates code, opens sources, and retains default control. This is the case for VueJS, Tailwind CSS, and Laravel, among others. Typically the lead developer either raises contributions directly like Evan You of VueJS, offer add-on services like Spark for Laravel, or the founders provide highly-paid consulting services.

3) **Non-profit** - This was Django’s approach early on, in 2008, when the Django Software Foundation was formed to promote, support, and advance Django.


## Django Software Foundation

- The DSF supports and maintains Django in a number of capacities. The largest expense, by far, is the Fellows Program, paid contractors who triage tickets, manage releases, and generally perform the unsexy but necessary work needed to keep Django on track.

- Tim Graham was the inaugural fellow during its 3-month pilot in the fall of 2014 and became a full-time fellow in 2015. He remained in this role until 2018 before transitioning to a part-time role. Carlton Gibson joined as a part-time Fellow in 2018 and in 2019 Mariusz Felisiak took over from Tim Graham.

- The Django Fellows do incredible, behind-the-scenes work for the community. You can hear podcast interviews with both Tim Graham and Marius Felisiak for more context.

- The DSF also supports projects related to Django such as the Kickstarters for Django REST Framework 3, improved PostgreSQL support, among others. It supports related conferences that promote Django and provides funding to extend access to a diverse group of developers. Manages things such as the recent redesign of the main Django website, and more. You can see a 2014 roundup for a broader sense.

- The DSF itself is run by a Board of Directors, who are elected annually by the ~180 individual members appointed by the DSF in recognition of their service to the Django community.

- If you make a donation to Django–and if you’re using Django professionally you really should–that money goes to the DSF. The majority goes to the Django Fellows who ensure the project remains on track and the rest helps promote Django and expand its community. The total budget for the DSF in 2019 is around $200,000, or less than the cost of a single Bay Area Django engineer.


## Technical Organization

The DSF handles legal, financial, and administrative matters for Django. But there is a separate organizational structure for the technical team.

Historically, Django followed Python’s model of having a Benevolent Dictator for Life, that is, a project founder who retained the final say for disputes/arguments within the community. Adrian Holovaty and Jacob Kaplan-Moss functioned as Django’s dual-BDFLs from 2005 until their retirement in 2014.

Django has a small, core team of trusted volunteers who work alongside the Django Fellows to manage the technical side of the Django Project. Django Core members are divided into teams that have authority over the Django Project infrastructure, including the Django Project website itself, the official issue tracker, official mailing lists, IRC channels, and more. There is currently ongoing discussion around potentially dissolving Django core or updating it in a meaningful way.