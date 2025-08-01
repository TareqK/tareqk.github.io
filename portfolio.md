---
layout: page
title: Projects & Contributions
subtitle: 
---

## j2htmx

Technologies : Java

Synopsis : htmx extensions for the j2html library

I learned of [htmx](https://htmx.org) and [hyperscript](https://hyperscript.org) while browsing literature on the origins of REST 
API design, and instantly saw the value in the use of HATEOAS(Hypermedia As The Engine Of Application State) in modern, distributed 
applications. I Had also previously learned of and used [j2html](https://j2html.com/), a typed HTML generator based on java.
I Created this extension to combine these 2 libraries together in order to be able to create fullstack web 
applications using using j2html, javalin, and htmx. More on this library can be found [here](https://github.com/TareqK/j2htmx)


## Javalin

Technologies : Java+Kotlin(Javalin), Javascript(Vue)

Synopsis : Improved and maintained the Vue plugin for the Javalin Library

I Came across Javalin while searching for lighter frameworks to use for smaller projects and internal tools. Javalin is a simple, no-CDI, code-first config lite framework for rest api's in java and other JVM languages. Simple, Easy to learn, and performant, I enjoyed using Javalin for writing my rest apis. As part of the library, there was a plugin that added Server-Side Routing for vue-based components without needing a build toolchain for javascript, using the client-side template parsing and building from vue.. I added a dependency resolver & optimizer, making the pages served smaller, by sending only the components that will be rendered in the page,  reducing some pages from 20kb Gzipped to 8 kb Gzipped, meaning that the server-side routing had significantly reduced cost and improved load times, and kept the sizes of individual pages constant even if the frontend of the application as a whole gets bigger. Additionally, I added support for Vue3, as the plugin only supported Vue2. These technologies were key in my success at my job as a DevOps engineer, allowing me to build tools fast and with a high ROI, with a decent user experience for my users(which are usually Devs and QA engineers). The Project can be found [Here](https://github.com/tipsy/javalin). More details on JavalinVue & It's use can be found [here](https://javalin.io/tutorials/simple-frontends-with-javalin-and-vue).


## EasyBus

Technologies : Java

Synopsis : Extensible Event Bus with Multiple Backing Implementations

Working in Domain-Driven Design, one of the key techniques that are utilized is the useage
of domain events in order to do orchestration and choreography. In a large and distributed
environment, It makes sense to use a message queue/broker or event queue in order to satisfy this.
However, in Domain-Driven Design practice, and by extension, in Microservices practice, its usually
a good idea to get started with a Monolithic application and move your way into a distributed one.

However, when doing so, I found no satisfactory in-memory event busses for Java. A Few candidates
spring to mind, such as JBus, but it had its own efficiency problems(such as the lack of 
caches for reflected methods and no scanning). So I decided to implement my own event bus, 
based on annotations and classpath scanning for handlers and events. The project itself is 
simple - annotate a few classes, and have a method with a specific signature ready, and then 
just pass in the packages you want to search for, and your events will be handled, and I even 
threw in some async handling for good measure. However, I used this project as a chance
to polish up my knowledge of Java Reflections, and the Reflections library. I also took 
it as a chance to learn more about writing compile-time annotation checkers, and even 
included one in the library in order to verify that the annotations used are correct
and the events being looked for made sense. Additionally, the bus can be backed by user-defined implementations, and includes implementations for a mongodb-backed bus and a rabbitmq-backed one. The Project Can be Found [Here](https://github.com/TareqK/easybus)


## Reveal-Control

Technologies : Java, Javascript

Synopsis : Plugin for [reveal.js](https://revealjs.com/) allowing presentation control from a secondary device

I have always enjoyed using the "everything-as-code" approach to any problem that can be solved by it, as to me, 
it greatly reduces cognitive load and tool switching. [Reveal.js](https://revealjs.com/) falls into this category of tooling, which allowed me
to also create presentations as code. 

However, reveal.js lacked in remote control functionality, which is why I wrote Reveal-Control, a server + frontend plugin
that allows one to control a reveal.js slideshow from a secondary device, including a mobile one, allowing a smoother
presentation experience for both the presenter and audiences in person. More about this project [Here](https://github.com/TareqK/reveal-control)

## Javalin Mithril

Technologies : Java

Synopsis : Created a Plugin for Javalin that uses mithril.js to create Multi-page applications.

The Idea for this plugin started off as a challenge : Could I write some form of a package and import system? Initially, I wanted to apply this to RE:DOM, as it was also a simple javascript framework. However, After discussing with the maintainer of javalin, he advised me to redirect my work and do this for mithril.js, which was a better known and used Web framework. What resulted was a plugin that allowed for server-side routing and state injection, while having a strong focus on class-based design for fronted frameworks. The name-spaced component system I built in this plugin allows for significantly larger projects compared to JavalinVue, and the Import system allows for very small and optimized web pages to be served. The maintainers of Javalin have accepted this project into their org, and the project can be found [Here](https://github.com/javalin/javalinmithril) and is available on Maven Central.


## OpenMyMed

The OpenMyMed project came about during the onset of the Covid-19 Pandemic. Inspired by the 
Open Source Covid-19 Supplies groups that popped up and the global Maker movement, I decided
to participate in this by providing software-solutions to help streamline the processing
of medical data and to create a lower barrier of entry to EMR systems and other related services.
The goal was always to be easy to self host and to build on, rather than to be complete or 
efficient, and to create community-local healthcare apps and services. The Organization
Home can be found [Here](https://github.com/openmymed/)

### Access.MD

Technologies : Java(Javalin,Hibernate), Vue.js, Android(Java)

Synopsis : An ICPC-2e based EMR and Telemedicine Platform

Access.MD started its life out as a covid-19 remote patient followup app, and grew overtime to 
become a telemdicine platform, including vitals checking using IR spectromtery from mobile
cameras.

We started out as a team of 3 software engineers, 3 doctors, and an experienced IT/Business
consultant  to help us streamline our branding. The webapp itself was initially built on 
RE:DOM using JSX templates(my favourite JS stack, as it allows me to be react-like while having
a much simpler lifecycle) , as I was the only person with any JS experience at the time, but
was eventually migrated to React.Js. We collaborated with some electrical engineers and academics
during our initial stages of development, and it was truly the first cross-functional team I 
ever lead, with people from all kinds of backgrounds from several countries. While I did handle
the backend development and operations (hosting, builds, etc), The experience I gained from this
project was more in Product Management, Team Leadership, and Communication, having to be at the
epicenter between technical people and domain experts for the duration of the project. The project
is currently looking for contributors, and I am still doing light maintenence work on it.

Another great thing about this project is that it touched on several areas of interest to me, 
both from a technology and an application domain point of view. The Project can be Found
[Here](https://github.com/openmymed/access.md), with more extensive design and collaboration
docs [Here](https://wiki.kisoft.me/doku.php?id=projects:access_md:start)

### Open-Fleetr

Technologies : Java(CRUDLets), JQuery

Synopsis : Ambulance Tracking and Dispatch system with reccomendation

Open-Fleetr was my second open source contribution. It wasthe first software I fully specified and delivered. The application itself was a 
tracking and dispatch application, with a rudimentary reccomendation system for ambulances and 
other emergency services. The application posed interesting questions and challenges, some of 
which I still have no answers to - such as creating navigation paths for vehicles that  are allowed
to go against street directions and into restriced areas. However, I learned much from this 
project in availability and replication - my main takeway in knowledge from this project
was in creating scalable and realtime systems, as the system itself was run on multiple 
machines, and at the same time, be able to provide real-time notifications and updates to 
dispatchers and drivers via websockets.

The project needs a re-write, but I want to persue it further, using more standard technology
(I built this over CRUDLets), and to enable medical providers to better utilize their resources.
The Project can be found [Here](https://github.com/openmymed/open-fleetr)

## Redom-App

Technologies : RE:DOM, ES6

Synopsis : Micro SPA fraemwork

redom-app was a weekend project that was an answer to this question I had : What is the smallest
Single Page Application framework you can create?  The answer was around 3 kilobytes compressed,
with 2KB going to redom and about 1KB going to the compressed router and middleware(which can
be optimized further with more strict minification). My main takeways from this project were
how routing works internally inside SPAs and how middleware injection works in JS. It was a 
fun weekend project, and I eventually published it to NPM and use it for whatever lightweigt
and weekend projects come to mind that need a simple UI. While it does have opinions on 
URLs and Middleware Capabilities, It mostly came down to common sense and practice, and 
was a fun project overall. I pushed this project to NPM for people to reuse. The Project
can be found [Here](https://github.com/TareqK/redom-app)

## JeSSE

Technologies : Java(Servlet, Jackson)

Synopsis : Implementation of the SSE standard in Java

Often times, when I was working, I needed to use Websockets or Server-Sent Events. Usually,
since these are handling application events from other places or database events, it was
near-impossible to use the JAX-RS Event Sink or similar JEE features. Therefore, I usually
wrote my own implementations of SSE using the plain servlet API each time. 

After some time, I decided to write a more standard library for this. The idea was to go 
against JEE ideals of having everything injected based on context and externally configured.
JeSSE delegates the management of SSE sessions and users to the developer, giving them more 
fine-grained control on authentication(instead of relying on the servlet container), 
and event delivery (instead of posting events globally or to one user). It allows developers
to Push Events to users even from background threads, allowing ... creative solutions such
as database polling to expand the capabilities of legacy systems and adding RTC capabilities 
to them. I would eventually revist this project at a later stage, and refactor it for code
quality and add testing and coverage as part of a Masters Project. The library is pushed
on maven central and is useable by all. The Project Can Be Found [Here](https://github.com/TareqK/Jesse)


## CRUDLets

Technologies : Java(Servlet,JDBC)

Synopsis : A Conventions-based REST api framework and ORM

CRUDLets was my first foray into open-soruce work. I was working on
a dispatch system for ambulances which I would later transfer to the openmymed organization 
to continue work on at a later time. For my own learning experience, and to get as
much knowledge as possible, I decided to explore more deeply the cocnepts
behind REST api frameworks and ORMs, and how they are build and behave.

To do that, I worked with the 2 lowest level APIs I could still deal with at the
time : JDBC, and the ServletApi. What I ended up doing was creating a very
strict conventions-only REST api framework and ORM with a rudimentary query language and 
role concept. the REST api framework  only allowed CRUD operations, and the name itself,
was a combination of "CRUD" and "Servlet"(the name RESTLets, was unfortunately taken).  

I Learned much from that project. The skills I got from it, from using IO Streams, 
Serialization/Deserialization, Writing DSLs and Fluent APIs, and Java Reflections, 
were a keystone in my career, and would come up again several times druing it,
especially when it came to debugging problems in other frameworks such as Hibernate 
or Jersey due to how similar the working concepts behind them were to my own work. 
It was a great learning experience, and I did manage to ship a project based on it.
The Project can be found [Here](https://github.com/TareqK/CRUDlets)


## Qahwagi

Technologies : Java(Javalin,Hibernate), RE:DOM, Flutter, Docker

Synopsis : Delivery App for coffee shops based on proximity

Qahwagi Started off as a fun idea we had while we were sitting down. When corona 
set in, and we saw that everything was moving towards delivery, we saw an opprotunity
to move into the market and began working on the application. The idea is simple : 
it provides poeple with a way to discover nearby coffee shops to their office or home,
and to order from those shops. The application is still work in progress, but is nearing
completion and will be available on app stores very soon.

## AbuTaxi

Technologies : Java(Jersey,Jackson,Jongo), JQuery.

Synopsis : Application to manage taxi office operations
 
AbuTaxi was a client project for my family business. As we are in the fields
of telecommunication, specifically, in the field of 2-way radio and RoIP, we 
often are in contact with people in the construction, transport, and security
industries. One such client, with a taxi office, requested from us to handle their
IT operations and to enable them to more efficiently manage their orders and customers. 
For that, we created a custom application that allows them to

- Manage their taxi licenses
- Manage Drivers
- Manage their vehicles & maintenance actions
- Manage their wireless radios(handsets)
- Manage their orders
- Produce reports on customers, orders, and drivers
- Manage their customers

The application is still in its beta-stages, but is nearing completion and 
being taken to production.

## Volunteer Work

- I'm an organizing Member of the palestinian open source community. My duties include
handling IT Operations and Software development for the group, Planning and 
Notation, giving webinars and creating e-learning content, in addition to professional
outreach.

- I'm a proponent of open education, and as such, have published several course notes
of my own for general public (see the education section of this website)

- I volunteer for arduino workshops with children whenver possible, and have given 
them as a volunteer with the AM Qattan foundation.


