+++
title = "Digital Garden"
date-published = "2025-01-17"
date-created = "2025-01-17"
date-modified = "2025-01-17"
description = "Mapping of digital garden theory concepts to archetype fields"
draft=true
author = "Zolletta"
tags = []
image = ""
effort = "high"
maturity = "evergreen"
node-type = "hub"
epistemic-status = "certain"
epistemic-intent = ""
humanness = "mixed"
trigger-source = "articles, newletters"
trigger-author-context = "Reading different aspect of internet culture"
+++
 

WIP

## Bibliographic References  

* [AI Dark Forest](https://maggieappleton.com/ai-dark-forest)
* [Digital Gardens](https://www.technologyreview.com/2020/09/03/1007716/digital-gardens-let-you-cultivate-your-own-little-bit-of-the-internet/)
* [Garden History](https://maggieappleton.com/garden-history)
* [Epistemic Statuses](https://devonzuegel.com/post/epistemic-statuses-are-lazy-and-that-is-a-good-thing)

## Mapping Table

| **Digital Garden Concept** | **Source**      | **Archetype Field**      | **Mandatory** | **Description** |
| ---------------------------| --------------- | ------------------------ | ------------- | -------------------------------------------------------------------------- |
| **Planting**               | Maggie Appleton | `date-published`         | **Yes**       | The date the note is first made public in the garden.                      |
| **Ideative Origin**        | Garden History  | `date-created`           | **Yes**       | The original date you started sketching the idea (often offline).          |
| **Tending**                | Digital Gardens | `date-modified`          | No            | Indicates the last maintenance or update to the note.                      |
| **Effort**                 | Garden History  | `effort`                 | **Yes**       | Indicates the intensity of research or work behind the note.               |
| **Maturity Level**         | Maggie Appleton | `maturity`               | **Yes**       | 🌱 seed, 🌿 seedling, or 🌳 evergreen.                                     |
| **Topology (Paths)**       | Digital Gardens | `node-type`              | **Yes**       | Defines node role: 🏛️ hub, 🍃 leaf, or 📚 collection.                      |
| **Humanness**              | *PROPOSAL*      | `humanness`              | **Yes**       | Authorship origin: 👤 human, 🤖 AI, or 🔗 mixed.                           | 
| **Epistemic Status**       | Devon Zuegel    | `epistemic-status`       | **Yes**       | Degree of certainty: certain, likely, uncertain, or speculative.           |
| **Epistemic Intent**       | Devon Zuegel    | `epistemic-intent`       | No            | What you expect from reader: feedback, corrections, reflection, discussion.|
| **Trigger Source**         | AI Dark Forest  | `trigger-source`         | No            | What caused you to write: conversation, book, intuition, experience, etc.  |
| **Trigger Author Context** | AI Dark Forest  | `trigger-author-context` | No            | When and where did ideas occur? Brief contextual note.                     |

## Maturity vs Epistemic Status

Maggie Appleton's **Maturity** tracks the effort and development of the post. It’s about the "gardening" process.
Devon Zuegel's **Epistemic Status** tracks the validity of the information. It’s about the "epistemology" (knowledge).

Example Scenario:

You have a note you've been writing for 2 years. It is formatted perfectly and very long.

Maturity: evergreen (it's a finished piece of work).

Epistemic Status: low confidence / speculative (it's a wild theory about the future that you aren't sure is true).

## Garden Topology

The articles emphasize that a garden is topological, not chronological. This is managed via the node-type field, which supports three primary values:

### Hub Nodes

High-level maps or "MOCs" (Maps of Content). They organize a broad topic but contain little original detail. These act as "Pillar Pages" that distribute authority across your site.

**Maturity**: Usually evergreen as they serve as the garden's permanent infrastructure.


### Leaf Nodes 

The atomic unit of the garden. Specific ideas, book summaries, or raw observations. Leaves link back to Hubs or other Leaves to create a "rhizomatic" web.

**Maturity**: Ranges from seed to evergreen.


### Collections 

A structured, linear sequence. Unlike a Hub (which is a map), a Collection is a "guided tour" through a set of thoughts or a learning journey.

**Difference from Tags**: While tags are flat, a collection implies a deliberate order or narrative thread you are cultivating.







