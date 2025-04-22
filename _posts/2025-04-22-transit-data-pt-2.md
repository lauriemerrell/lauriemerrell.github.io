---
title: "So you want to do a public transit data project, part 2: Ridership"
date: 2025-04-22 17:00:00 -0500
categories: ["Public Transit", Data]
tags: ["working with transit data"]  
description: "Fundamental concepts in transit ridership data."   
image:
  path: /assets/img/posts/mike-cox-9bsLrU6bf_w-unsplash.jpg
  alt: A photo of a CTA Purple Line train on elevated tracks in front of a stone building.
---
*This is part 2 of an introductory series on working with transit data. [For part 1, see here](/posts/transit-data-pt-1).*

# Ridership data

Ridership data refers to data about how many people used a transit system, which on its face might sound pretty simple. “How many people rode the CTA today?” probably seems like a question that should have a pretty straightforward answer. However, things can get more complicated quickly. 

Because it is required for [National Transit Database](https://www.transit.dot.gov/ntd) reporting, ridership data is available for most agencies in at least some form. To make the most of it, you'll want to understand some key concepts and consider the following factors to make sure that you understand the data that you're working with.

## Counting people vs. counting rides

The number of unique **people** who rode on the system is different from the number of **rides or trips** that occurred on the system. For example, one person commuting to and from work results in two trips. 

Ridership data is almost always reporting **rides** rather than **riders**. It is often based on either fare (payment) or APC ([automated passenger counter](https://www.transitwiki.org/TransitWiki/index.php/Automated_passenger_counter)) data, which counts instances where a rider pays a fare, boards a vehicle, or enters a station. 

While some fare payment data may be able to be reconciled to actual riders (for example by grouping together taps of the same farecard), this is not the common practice when reporting ridership counts.

### Linked vs. unlinked trips
 
There is one more specific flavor of the riders vs. rides question that data users should understand: "linked" vs. "unlinked" trips. A “linked” trip is a distinct total journey, including any transfers, while an “unlinked” trip counts each leg of a journey (each time the rider boards a vehicle) as distinct. For example, if I ride the #72 North bus to the North/Clybourn Red Line station and transfer to the train to get to my final destination then I have taken one “linked” trip but two “unlinked” trips. 

As described above, most ridership data is based on individual fare payment, vehicle boarding, or station entry actions, so it is usually reporting unlinked trips. Unlinked trips are what is reported to the NTD.

One important special case is “cross-platform transfers” (a transfer where a rider does not have to pay a fare or enter/exit a station to switch between vehicles, like within the Chicago Loop elevated train stations). These may or may not be counted depending on the specific methodology or source you’re looking at. 

## Reporting level

Ridership can commonly be reported at several different levels:

 * **Stop/station**: If you have stop- or station-level ridership reporting, you should be mindful of how you’re handling stops that are served by multiple routes or stops that serve multiple directions for the same route (for example, many train stations).  
 * **Route/line**: If you have route- or line-level reporting, you may need to investigate how different variants of the route (for example, different directions, branched or extended route patterns, overnight vs. daytime service) are handled. 
 * **Mode**: Mode refers to different types of service defined by vehicle type, service pattern, and grade separation; for example, modes can include bus, metro/subway train, commuter/regional train, trolley, ferry, etc. For mode-level reporting, you will need to understand how the data source defines its modes – which routes are counted as trolleys vs. buses? Which routes are commuter vs. heavy rail? Mode-level data is what is most readily available in the NTD.

## Time period

For any data analysis project, you need to understand the time units in which your data is being recorded/reported. This is especially true for ridership data, and doubly so if you are trying to compare data across different agencies or sources. 

Some agencies or sources will publish only daily, weekly, or monthly **totals**. Others will post **averages** by day type: in transit, weekdays and weekends often have significantly different levels of service, and ridership can vary accordingly. Whatever units the agency uses, it’s worth thinking through what the impacts might be on your use case. 

## Gathering context

As with any data project, some knowledge of conditions on the ground is always useful. If you see something weird (big spikes or declines, missing data, etc.) in your ridership data, it may be worth trying to look for local news coverage or the agency’s old social media posts to see if something unusual was going on during your period of interest (for example: was a new route added, or an old route removed? was there a significant construction project or a special event?)

## NTD reporting

Finally, it’s worth noting that National Transit Database reporting is one of the most important use cases for ridership data from the agency perspective, and the NTD has very strict rules for how to use automatic passenger counter data to report to them (see [this white paper](https://www.oregon.gov/odot/RPTD/RPTD%20Document%20Library/APC-AFC-White-Paper-Trillium-2021.pdf) for a helpful overview), including how to treat the data as a sample and whether or how it should be scaled up. NTD guidelines may affect what data agencies make available and how they calculate it. 

## Postscript: CTA ridership data

Given that I am in Chicago, I wanted to include a few notes on working with CTA ridership data in particular. You can access CTA ridership data from a few different sources:

* [The City of Chicago Data Portal](https://data.cityofchicago.org/Transportation/CTA-List-of-CTA-Datasets/pnau-cf66/data_preview) – The Data Portal offers machine-readable flat files that are useful for code or spreadsheet-based analyses.

* [PDF reports on the CTA website](https://www.transitchicago.com/ridership/) - Because these are PDFs, they’re not as accessible for automated use **but** they provide a lot more insight into the methodology that the CTA uses to count ridership. The PDFs contain a “How to Read This Report” page that explains how the data is collected and reported, and includes helpful metadata like the number of service days by type in the given month (this can help clarify how things like holidays were treated in the data).  

    The PDFs also break down how the CTA treats ridership at rail transfer stations (stations serving multiple routes) which frankly is confusing and could probably be its own post. For example they seem to allocate all ridership at Fullerton and Belmont to the Red Line, and they treat the Loop stations as totally combined and don’t allocate by line at all. **It’s worth cross referencing these PDF reports with other, more accessible sources to understand how things are being counted.**


* [The RTA also hosts ridership data for the CTA](https://www.rtams.org/ridership)

*Post photo by [Mike Cox](https://unsplash.com/@iprefermike?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash) on [Unsplash](https://unsplash.com/photos/gray-train-on-rail-road-during-daytime-9bsLrU6bf_w?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash)*

