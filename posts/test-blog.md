---
title: "This is a test blog"
slug: "test-blog"
excerpt: "AI is rapidly automating cognitive labour, transforming workplaces. Effective data management is crucial, yet much tacit knowledge remains undocumented, causing inefficiencies and challenges during staff transitions."
coverImage: "/blog/the-future-of-ai-data-management.webp"
category: "Data Management"
date: "2025-10-05T10:23:07.322Z"
author:
  name: Gavin
  picture: "/blog/letter-g.png"
ogImage:
  url: "/blog/the-future-of-ai-data-management.webp"
---

AI is going to change everything. In former times automation was focused on replacing mechanical labour. We moved from bio-power, the use of horses and Oxen, and water-power, the use of water wheels, to a mechanically driven world running on oil (and sometimes nuclear power) to remove direct human toil from a great number of tasks. This in turn created enormous increases in human productivity and drove us into the information age, where cognitive labour was key to productivity.

The AI revolution is now in the process of automating cognitive labour. While current LLMs cannot replace humans in all cognitive tasks, they can replace a surprisingly large number of tasks. Many people will simply become much more productive by offloading cognitive labour to agents. Some jobs however will be completely automated. Just as factories today have vastly fewer people than in the 20th century, the firm of the mid-21st century will need far fewer knowledge workers than the first part. 

The rate of this process is also going to be far faster than the automation of human labor. Because the labour of implementing AIs is itself cognitive labor, we now can use AIs to accelerate the process of replacing cognitive labour with AIs. This will lead to an exponential productivity growth process. A virtual cycle as it were.

## Data Management Now

Which brings us to the problem of data management. In the firm, as it currently stands, there are lots of data assets which are required for operations and reporting. The operational data of a modern firm is often maintained in the cloud, using either a data lake, a data warehouse or some admixture of the two. 

The location of relevant data in a firm is sometimes assisted with various metadata catalogues, data catalogues etc. especially for those following best practices.  However, very often a large amount of tacit information is maintained in the brains of current staff. 

When new staff join, they spend some period socializing into firm behavior and become effective agents by the transference of this tacit knowledge about what is stored where from current employees. 

This process is already quite error-prone although difficult to avoid and expensive to avoid, as employees are not terribly motivated to keep detailed documentation and metadata about every resource. The extra process is painful and often deadlines and other important tasks push this important step off the stack. Further, since humans can socialize to get around the problem, it does not feel as crucial as it perhaps is. The pain becomes especially acute when turnover is high.

![Obtaining data context can be time consuming](/blog/obtaining-context-about-data.webp)

## Context is King

As we enter a world of AI agents, context is everything. Our agents can perhaps ask current employees to inform them of the context, and while this is part of the solution, it is also time-consuming. Sometimes context comes with the data or can be inferred from it. If you get an email that has some text about an Excel file for instance, this email thread should be considered context which an AI should be allowed to use to inform its processing of the data.

And they will also need to tell each other. The workplace is now going to have cognitive agents as first-class citizens and to make that happen we need to make context explicit, well-structured, stored in discoverable locations and available to the LLM when they look for it. 

Making context recoverable by an LLM is a retrieval process. And this means it will have to be using retrieval technologies. Some old technologies are likely to be of use here in some instances, such as full-text search. Some newer technologies will also be important, such as dense vector search, and some bleeding edge approaches utilizing LLMs themselves for recovery, or at least their attention, will also come into play.

![Robot AI obtaining context from data](/blog/ai-agent-obtaining-context.webp)

## Socializing with Cognitive Robots

The process of getting these LLMs to write down the correct contextual information so it is discoverable will be part of data management which is every bit as important as the data itself. What kind of context do we need to record?

The first process for data can be thought of as "title search". When we have a table or a graph object or whatnot, we need to explain what it contains very precisely. We need not just attribute names, not just their types, but their meaning and how that relates to the other data fields. We need to explain about its expected data quality. We need to know its units. All of these things will be discoverable via tools provided to the LLMs so they can make appropriate decisions. This means that the data itself can be stored in a variety of ways as long as it is made available by a tool to the LLM which needs to make decisions. This is how the LLMs can socialize information. Instead of a water cooler, they will be talking to a context database.

![Robots chatting around a water cooler](/blog/robots-chatting.webp)

## How do I get this Context Filled?

The answer to how to fill this context is data preparation. This includes data ingestion, data cleaning, data analysis, data transformation and data archaeology. The easiest way to prepare context appropriately is during the ingestion of data or by applying a process of context enrichment to current data resources.

And all of this will be done by AI tools. And when we say "will" we do not mean in the far future, but in the immediate future and that future is already starting now. We have started the journey of data preparation for AI, and while it is far from complete, the proof is already in a quite delicious pudding that we've created as a demo.
