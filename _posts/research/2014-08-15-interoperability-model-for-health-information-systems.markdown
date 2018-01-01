---
layout: post
title: "SDMX-HD"
modified:
categories: research
excerpt: Insignt into an Interoperability Model for HIS. 
tags: []
img: sdmx-hd-logo.png
image:
  feature:
date: 2014-08-15T22:41:51+05:30
---

## Background
Recent IT advancements have resulted digital collection of health related information. There
exist diverse health information systems today, each addressing a specific need in the healthcare
domain e.g. Hospital Information System collecting clinical, patient and administrative data;
Health Management and Information Systems (HMIS) collecting health indicators across an
area (such as mortality, births and vaccination) and systems for Telemedicine to provide access
to healthcare for areas that are not easily accessible. Integrating the information collected
across such diverse systems can be technically challenging, primarily due to the different data
models and work 
ows being adopted to address specific requirements catered by such systems.
However, such integration can provide significant benefits such as single point of access, detailed
and real-time analysis and reduction in duplication of information.
In this project, we integrated OpenMRS based hospital information systems
and DHIS2 based HMIS deployed across the state of Himachal Pradesh (HP), India. **OpenMRS
based system is now deployed across 20 hospitals in the state while the DHIS2 based system is
used for data collection from multiple reports under NRHM program.** We used WHO backed
interface for statistical data and metadata exchange in healthcare called SDMX-HD for data
communication across the systems. We present the system architecture in detail and provide
discussion on challenges and learning from development and deployment of such a system across
the state of HP. We also discuss the data being collected at present and some analysis which
can done to get useful insights from this data. We also looked into some external factors which
might be influencing the healthcare setting in the state.

## System Design
Below is the design of the interoperability architecture. It shows the interactions between the DHIS and
OpenMRS and how the data between the two systems is exchanged using Dhisreport module.
![Jiah Architecture]({{ site.url }}/images/sdmx-hd/sdmxhd-arch.PNG)

## Field Study and Data Collection
The field study was done in multiple stages which resulted in several design improvements for the next iterations of the module. Lifecycle of the project was as follows :-
1. Fix technical issues with the existing SDMX-HD Module.
2. Deployment which was followed by field visits.
3. Additional improvements in the module to solve issues with uptake.
4. Collect statistical data from module deployment.
5. Correlate findings from the module data with external factors such as Weather, Air Pollutiona and Water Pollution.
 > Details of each of the phase along with observations from the field study are covered in detail in the report cited below.

## Resources
Mehra, A., & Singh, A. (2014). Interoperability model for health information systems and associated benefits challenges and approach (Doctoral dissertation, IIIT Delhi).[pdf]()