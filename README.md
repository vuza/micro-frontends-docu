# Micro Frontends: Documentation

This repository describes various concepts which allow development and deployment of Micro Frontends.

**Personal motivation for this repository**

- **I implemented a POC covering this topic**, and am happy for every input: ["POC I implemented using Project Mosaic"](#poc-i-implemented-using-project-mosaic)
- Also, **I'm looking for a couple of people** and/or external input to answer questions covered at ["Future research"](#future-research)

## Contents

- [What are Micro Frontends](#what-are-micro-frontends)
- [Motivation](#motivation)
- [Various approaches to build Micro Frontends](#various-approaches-to-build-micro-frontends)
    - [Project Mosaic](#project-mosaic)
- [Future research](#future-research)
- [External sources](#external-sources)

## What are Micro Frontends?

> The idea behind Micro Frontends is to think about a website or web app as a composition of features which are owned by independent teams. Each team has a distinct area of business or mission it cares about and specialises in. A team is cross functional and develops its features end-to-end, from database to user interface.

micro-frontends.org

## Motivation

In an ideal world a single team has a mission or business value to fulfill and has all tools to be capable to do so in its hand. With traditional web applications this is impossible to realize. No matter which technology you choose, in the end your React.js, Angular or Vue.js application gets compiled to a huge frontend monolith. However, similar to microservices in the backend, you should enable your team to have their own release cycles, tools sets and deployment. If a team's mission is to build a webshop's cart application it should be able of fulfilling this task by developing everything from storage and logic to the UI and therefore be a real vertical team. To allow vertical teams in combination with web applications you need a UI composition strategy to sew everything together at one or the other point.

![Vertical Teams with Micro Frontends](./vertical_teams.png)

## Various approaches to build Micro Frontends

When I talk about Micro Frontends, I talk about web based GUIs which are composed at runtime. If multiple applications get sewed together at compile time, the Micro Frontend concept does not solve problems like independent release cycles, high exchangeability and free choice of technology.
Furthermore Micro Frontends can be rendered at the server or client, both approaches are valid, can be mixed and might have their own dis- and advantages.

### Project Mosaic

... is a collection of tools, allowing server- and clientside rendering of Micro Frontends. The project contains tools like Tailor.js for UI composition, Skipper for HTTP routing and Tessellate for SSR. I implemented a POC using a couple of Project Mosaic's tools. The tools I didn't use, are largely un-documented or not open source.

#### POC I implemented using Project Mosaic

I implemented three natively server side rendered React.js applications, composed with Tailor.js and routed with Skipper: Cart, User and Product Highlight application

![Micro Frontends in real life](./micro_frontends.png)

Have a look at the applications and service setups and their documentation and [my blog article](https://blog.senacor.com/microfrontends/) to understand the details of this POC:

- [Cart application](https://github.com/vuza/micro-frontends-cart)
- [Product Highlight application](https://github.com/vuza/micro-frontends-highlights)
- [User application](https://github.com/vuza/micro-frontends-user)
- [Tailor.js setup](https://github.com/vuza/micro-frontends-tailor)
- [Skipper setup](https://github.com/vuza/micro-frontends-skipper)

## Future research

Now we understood the challenges and have a very simple solution to most of them, we should invest time in further research. Can client navigation can be made possible without too much framework overhead? How big is the disadvantage of SSR only solutions? How can Micro Frontends communicate in the frontend? How can they communicate in the backend?

### Next tasks

In order to extend this (or a similar) repository with many other possible approaches and their (dis-)advantages I want to extend the current Micro Frontends webshop POC or build a new Micro Frontend webshop based on the current one's key learnings.

**Questions to be answered**

- What are the possibilities to manage an application's layout which is build out of Micro Frontends?
- What's the best possible way to render web apps on the server side for this problem?
- How and where is state, needed for server side rendering, as well as for business processed, stored? Can JWT be used for both problems?
- How can shared dependencies like menus, buttons and other design elements be implemented and used?
- How can CSS scoping preferably be archived?
- How can Micro Frontends can communicate in the browser?
- How can local development of Micro Frontends best be made possible?

**Iterative goals**

I propose the following very high level and time boxed goals for one or two week sprints,depending on available time, in order to answer above questions and fill this repository with many more learning about different approaches.

1. A full functioning UI composition framework was found, documented, set up including CI pipeline, deployment description and only waits for the implementation of Micro Frontends.
2. Each Micro Frontend has a basic implementation, it either delivers pre-rendered HTML or a JS module, which gets rendered on the client side. It includes scoped CSS and JS and has basic functionality. The UI composition solution can show all these Micro Frontends.
3. JWT or an comparable concept gets used to build stateless applications and enable server side rendering. The UI components can communicate on the client side. Authentication will be necessary for this features.
4. Each Micro Frontend and the overall solution is documented, so that it can be used for blog article, conference talks and further trainings.

## External sources

Although Micro Frontends still is not a well known paradigm, there are a couple of people working on that concept.

- A whole domain dedicated to this topic: http://micro-frontends.org
- Talk about transclusion: https://speakerdeck.com/lapaqui/transklusion-kitt-fur-gut-geschnittene-webanwendungen
- ToughtWorks technolog radar promoting Micro Frontends: https://www.thoughtworks.com/radar/techniques
- A great and big collection of sources around this topic: https://micro-frontends.zeef.com/elisabeth.engel?ref=elisabeth.engel&share=ee53d51a914b4951ae5c94ece97642fc
- Zalando's Project Mosaic: https://www.mosaic9.org/
- Blog article explaining the paradigm: https://medium.com/@tomsoderlund/micro-frontends-a-microservice-approach-to-front-end-web-development-f325ebdadc16
- Project Mosaic talk: https://www.youtube.com/watch?v=FdJ_-4v2CzE
- Great collection of videos covering Micro Frontends from Elisabeth Engel from gutefrage.net: https://www.youtube.com/watch?v=fZW5nY3SePY&list=PLI1AtZo9B3YL_xpi19IuxFcTuCi2_thQT
- Of course my own blog article on how i built a very simple webshop with Micro Frontends: https://blog.senacor.com/microfrontends/

... find many more resources at each of above listed links!