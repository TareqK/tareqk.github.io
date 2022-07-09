---
layout: post
title: Feature Branches and Trunk Based Development
subtitle: Or, How I learned to stopped worrying and embraced the chaos
date: 2022-07-09
published: true
---
# Feature Branches and Trunk Based Development

Feature branches - or to be exact, long running feature branches in a mid-large team environment, tend to cause integration issues because of sync lag and design lag.

For example, if I were to be working with full, long running(4 days+,for me) feature branch for a modestly sized SAAS offering, clocking in around 1 million LOC, I could easily be modifying dozens of files and hundreds of lines per feature branch. In an ideal world, these changes can and would be communicated across the entire organization ahead or just in time, to avoid multiple people changing in the same area for the duration of work.

However, in any practical scenario this tends to fall apart fairly fast if key individuals(and it really comes down to key individuals doing a *lot* more than they ought to be) are not there to manage communication cross team. Management - even technical management - eventually gets disconnected with facts on the ground at some point.

If you have an project with say, ~30 developers, each putting in a pull request every week or so, you end up with 90 or so pull requests every month, usually having 10-15 active at any given moment. If You were to handle these pull requests first come first serve, you also end up having to re-integrate changes in the mainline to each pull request branch every time you merge another pull request in - which takes a lot of time, effort, and duplicates work, as these branches have a lot of work on them that needs to be reintegrated(hundreds of lines, dozens of files).

Contrasted to this is the simplified Trunk-based flow. By breaking down features, using feature flags(the most important part of any TBD or CI flow), and integrating the work of a feature into mainline multiple times per day, you end up with smaller reviews of smaller changes - more likely to be reviewed more diligently, and less likely to cause disastrous changes across the board. 

Additionally, as your work is on mainline, and everyone is pulling in mainline to their work(or ought to be anyway), the chances of a conflict become lower as your changes are smaller and more incremental, and other people on the ground will be able to see the direction you are working in and either follow you or suggest corrections faster. This means that even if the organization keeps growing to 50,60,200 developers and more, the people who *need* to know what you are doing, will by nature of this flow *see* what you are doing, as you are doing.

Trunk Based development does not mean you have *no* branching, it just means that branches are smaller, oriented to slices of features rather than whole features, and exist to ensure quality reviews and checks, rather than a way of siloing off the development of different features. Everything is integrated as it is being written, and feedback is much, much quicker(we all had that *one* review we kept pushing to the end of the week because its 300 files and 1500 LOC, and just end up giving a hap-hazard "ok" to)

The details on *how* to do TBD are over [here](https://trunkbaseddevelopment.com/), but the general gist is to keep everything going in one straight line rather than a million independent lines that meet again.

This is just us applying KISS(Keep it sweet and simple) to our code process - rather than having a procedure for every scenario, we treat everything the same and move in one direction all the time - into trunk, and forward.
