---
title: "AI Driven Citation: Controlling Hallucinations With Concrete Sources"
slug: "ai-citation-controlling-hallucinations-with-concrete-sources"
excerpt: "This process, which I call “citation under question” because it does a deep read through the entire document with a question in mind, taking notes about sections that answer the question, is precisely what the bookwyrm.ai citation endpoint is designed to solve."
coverImage: "/blog/robot-dragon-assisting-taking-notes.webp"
category: "Data Workflows"
date: "2025-10-06T04:27:23Z"
author:
  name: Gavin
  picture: "/blog/letter-g.png"
ogImage:
  url: "/blog/robot-dragon-assisting-taking-notes.webp"
---

Recently I had the amazing opportunity to discuss Artificial Intelligence for research with Dr [Peter Turchin and his group](https://csh.ac.at/peter-turchin/). Dr Turchin researches long-scale historical dynamics using quantitative methods.  As such, he and his group have to dig up data for historical events which have a relative paucity of statistical data as compared to our more modern data-flooded age.

In order to increase their coverage and depth, they have been very tech-forward, utilising AI methods to increase their throughput. The use of AI in an academic context has to be managed very carefully since all data which is utilised has to be carefully reviewed by expert researchers.

Despite these challenges, some of their research work *can* be automated. The trick is to make the AI do a lot of the drudgery and surface only a small amount of reviewable information to experts.

They showed me some of their current pipeline and asked me for suggestions on what might be useful in speeding things up. This pipeline already uses AI extensively to catalogue potential historical events which are to be verified. The verification step is still, however, almost completely manual.

This led me to suggest the architecture in Figure 1. The problem is essentially this:

* We have a document which is said (by an AI) to contain information about a given event.
* We need to read through this document and find quotations which evidence the event and use them as exact citations.
* These exact citations with their excerpts need to go to an expert for review.

The key insight which makes this possible?  We only return concrete citations of real documents.

We need to recover the exact text from a primary source which lends
evidence to a claim. Hallucination can then be relegated to unsupportive excerpts. In order to do this, we can use a simple Large Language Model (LLM) to do a lot of the groundwork. When I say a *simple* LLM, I mean in the sense that it is not one of the gigantic GPT5 / Claude Sonnet 4 etc. models which have hundreds of billions of parameters, but one with perhaps only 20 billion. Smaller LLMs can act much faster and therefore traverse more data rapidly. This LLM reads the entire text and tries to extract position information for supporting citations. Since we are extracting position information, hallucinations will simply lead to either the wrong part of the text or positions which do not exist, but we will not just make text up ever.

We call this process “citation under question” because it does a deep read through the entire document, with a question in mind, taking notes about sections that answer the question. This is precisely what the bookwyrm.ai citation endpoint is designed to solve.

From here, we get a relatively small number of candidate citations. These citations may not be very accurate because our relatively unintelligent model may have made some mistakes. So we use a big LLM to review the outputs and throw out anything which does not look viable. At this point, we have true exact quotes from the source document, which have been reviewed by a smart AI and which can now be given directly to an RA (Research Assistant). They will pass or remove, and finally, a senior researcher will be given the data for a final check.

Implementing this sort of deep-read citation process can save huge amounts of time, given the size and scale of many historical texts, which can run into the many 100s of pages. And it all happens relatively fast. A complete event search in [The Oxford History of the French Revolution](https://en.wikipedia.org/wiki/The_Oxford_History_of_the_French_Revolution), which runs in at 496 pages, took only a couple of minutes.

But perhaps best of all, the process of writing the [citation workflow](https://github.com/scidonia/citation-workflow) prototype took me literally 1 hour and 15 minutes. I simply pointed my AI at a page for BookWyrm designed to expose library [documentation specifically for AIs](https://bookwyrm-client.readthedocs.io/en/latest/ai/) and told it the process it should undertake in a single prompt. This took about 5 minutes. The next hour was debugging (and it turned out that there was a bug in the BookWyrm client, which needed to be fixed!). AI can not only help to automate, but it can automate the automation!

The process is, of course, currently only a prototype but it is fully usable (and resumable should it crash at any point!) and can work on documents of a few hundred pages without difficulty. This process presents a host of possibilities for research acceleration across a wide variety of domains.

If you think your problem might benefit from this sort of approach, why not [give bookwyrm.ai a spin](https://bookwyrm.ai/beta)?

![Figure 1: Architecture](/blog/workflow_diagram.webp)
