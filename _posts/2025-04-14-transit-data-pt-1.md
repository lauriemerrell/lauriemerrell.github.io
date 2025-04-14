---
title: "So you want to do a public transit data project, part 1: Working with common sources"
date: 2025-04-14 17:00:00 -0500
categories: ["Public Transit", Data]
tags: ["working with transit data"]     
image:
  path: /assets/img/posts/jeremiah-higgins-lzBHm2sbJPM-unsplash.jpeg
  alt: A photo of a CTA Brown Line train at the Sedgwick station with bright sun glow.
---

# Getting started with transit data

Public transit offers fertile ground for tech and data projects. There is abundant publicly-available data, including geospatial, temporal, financial, and other common data types, often with at least some historical coverage. Plus, you know, people love trains. 

Public transit data can also be tricky. The data often comes in formats and sources that may not be familiar, there is industry jargon, and there’s a lot of variation from agency to agency. 

With that in mind, I am planning a series of posts to cover some key concepts and common data types related to public transit. I have worked professionally in the public transit data space and I’ve also done volunteer civic technology work with transit data. I’ve seen how transit data is often used by people who are engaging in journalism, volunteer, or side projects, and I hope that these posts can help people who are excited about transit data but aren’t totally sure where to start. 

These posts are most likely to be useful to people who have some familiarity with data analysis but who are not domain experts in public transit. I come from a data analytics background, not from an urban planning or transit operations background, so apologies to the planners of the world if my framing is sometimes imprecise. 

So, with all that said, let’s get started with a quick overview of some of the most common types or categories of transit data.

## Types of data

The following types of data will often be available across agencies.

* **Ridership data**: Ridership data includes counts of how many trips were taken on transit during a given time period. Ridership data can help you answer questions about the usage level of different transit services in your community. For example, you would use ridership data to determine which bus route is most popular for a given agency. Ridership data will be covered in more detail in Part 2. 
* **Schedule data**: Many transit agencies publish their schedule in a special dedicated data format called [GTFS (General Transit Feed Specification)](https://gtfs.org/schedule/). GTFS data tells you what the agency’s routes are, where they stop, when and how often they run, etc. Schedule data can help you answer questions about levels of scheduled transit service: for example, which is the most frequent bus in your community, or how far you can travel from different neighborhoods based on their available bus or train service. Schedule data also includes the geographic information you would need to make a map of transit lines or stops. Schedule or static GTFS will be covered in more detail in Part 3. 
* **Realtime data**: In the last 5-10 years, it has become more common for transit agencies to publish realtime data about their services, including the realtime vehicle tracking and predictions that you see in transit apps. For example, realtime transit data is what you would need to show when the next bus is going to arrive for a given bus stop. Realtime data will often be published in the [GTFS-RT data format](https://gtfs.org/realtime/reference/#).
* **Other operational data**: Operational data could include information like how many vehicles an agency operates, the agency’s budget, information about agency staffing, the agency’s safety record, etc. Things like on-time performance for an agency might be published as part of its operational data reporting as well.

## Common sources

The common data types listed above are often available through standardized or similar locations across transit agencies. When you’re looking for this data, you might find it in one of the following places:
* The [National Transit Database (NTD)](https://www.transit.dot.gov/ntd) is a federally-maintained database of information about public transit in the United States. The NTD offers a [whole host of data products](https://www.transit.dot.gov/ntd/ntd-data), covering ridership and some operational data. Before using any NTD data, I recommend consulting the associated data dictionary file and the [NTD Glossary](https://www.transit.dot.gov/ntd/national-transit-database-ntd-glossary). NTD products often include technical terms and abbreviations, and you should check the documentation to make sure you understand what is being counted. 
* GTFS and GTFS-RT data will often be posted on a “For Developers” (or similar) page on an agency’s website. For example, [here is the CTA’s page](https://www.transitchicago.com/developers/) for Chicago and [here is the MTA’s page](https://new.mta.info/developers) for New York City.
* Transit agencies may publish ridership and operational data either on their own data portal or on a data portal hosted by a related government entity. For example, the RTA in Chicago provides [a data portal](https://www.transit.dot.gov/ntd/national-transit-database-ntd-glossary) that includes employee, budget, and ridership data for all three Chicagoland transit agencies (CTA, Metra, and Pace). The MTA in New York City has [its own open data program](https://new.mta.info/open-data).
* Smaller transit agencies may publish ridership and operational data in board meeting minutes or planning reports that are hosted as PDFs on their website or on the website of an affiliated government entity. These can be painful to work with but if you’re really interested in a specific agency, it may be worth it to try to track down meeting minutes and PDF reports. For example, [SMTD (Springfield, IL) has a page on their site with budget and compensation data in PDF form](https://www.smtd.org/statsanddocs), and [Danville Mass Transit (Danville, IL) reports data monthly to their city’s Public Works Committee](https://www.cityofdanville.org/AgendaCenter/Public-Works-Committee-8).

## Example projects

It can also be helpful to start by looking at existing related projects and, if available, their code and data sources. Some Chicago-focused transit data projects that may provide some inspiration include:

* (Shameless self-promotion) [The Ghost Buses project’s analysis of bus reliability](https://ghostbuses.com/)
* [The StopWatch project from the Mansueto Institute & Chicago Tribune](https://ctastopwatch.miurban-dashboards.org/)
* [Brandon McFadden’s CTA, Metra, and WMATA rail reliability trackers and transit data APIs](https://brandonmcfadden.com/)
* [Commuters Take Action’s service cuts analysis](https://www.ctaction.org/service-cuts)
* [WTTW’s analysis of operator overtime](https://news.wttw.com/2024/03/12/cta-continues-rely-bus-and-train-operator-overtime-fails-provide-detailed-information) (and [subsequent correction](https://news.wttw.com/2024/04/01/cta-data-shows-reliance-overtime-chronic-foia-delays-and-years-mischaracterized-records))

These lists (especially the example projects) are far from exhaustive, but hopefully they provide some helpful pointers for anyone who is trying to figure out what data they need and where they might be able to find it. Happy analyzing!

*Post photo by [Jeremiah Higgins](https://unsplash.com/@jerem1ah_h1gg1ns?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash) on [Unsplash](https://unsplash.com/photos/gray-train-on-black-metal-rail-road-under-white-sky-lzBHm2sbJPM?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash)*