---
layout: single
title:  "A Modern Antibiotic Resistance Reporting System"
excerpt: "An overview of the specifications for a yet-to-be-created antibiotic resistance reporting system."
category: antibiotic
tags: [build, antibiotic resistance project, overview]
comments: true
---

## Foreword:

This project was conceived at the end of 2016 as I was considering solutions for meeting the various antibiotic challenges that were accepting applications at the time. Unfortunately, I was underprepared and didn't submit an application while I could. Since then, the idea has continued to incubate in my mind for several months before being transcribed into a steno pad, followed by an electronic notebook, now followed by my website. I believe this modern approach would revolutionize how we characterize antibiotic resistances and ultimately other medical complications. As a result, the trajectory of global antibiotic resistance would be stalled or even reverted by more efficient and informed treatments.

**If I truly believe this is a revolutionary idea - *Why post it openly on this website?***

I agree that it probably is quite naive for me to do this, but I don't have the resources that I need to execute this idea in a timely manner and I believe this idea should be realized. By posting it in the open, it will only be a matter of time before someone stumbles across it or the data scientists at Google discover what their web crawler has uncovered. I wasn't able to join the well funded challenges several months ago, so I have started my own. Can I produce this system before another company? It is true that I would really like to be the one who sees this idea come to fruition, but I believe that the benefit that the world would receive from this system would out do any benefit that I would receive. Why should I hold back tangible technological advancements for my own personal gain?

The clock has started ticking and it is only a matter of time before either I or some unknown character produces this system.

Let's get going - Game on.

## Objective:

Develop an affordable, distributed antibiotic resistance reporting system that collects and displays information in near-realtime to both characterize resistances in patient samples within a clinic and monitor the spread of resistances over space and time.

## Product Specifications:

1. **Requirement:** identify antibiotic resistances in patient samples quickly and accurately.
2. **Requirement:** minimize the cost barrier as much as possible so that nearly any clinic in the world can afford this system and contribute to the global data repository.
2. **Feature:** report probabilities of being infected by different organisms.
3. **Feature:** produce an interactive spatial-temporal map characterizing the prevalence and spread of different resistances in near-realtime.

First and foremost, in order for this technology to be adopted, it must satisfy the needs of clinics extremely well - it must be affordable and able to operate as a standalone unit in remote locations while also providing quality information. Its core purpose is to report antibiotic resistances within patient samples.

If the clinic permits the machine to communicate with an offsite server, additional benefits would be made possible due to access to greater computational power. Assay reports would be forwarded to a server that processes the data through a machine learned algorithm to identify the likelihood of being infected with a given organism. This would be reported back to the clinic. Also, the server will insert the report into a global database consisting of time, location and resistances reported, which would be available as an interactive map online.

## Proposed Assay:

1. Sample is microfluidically transferred to a cartridge containing concentration gradients of multiple antibiotics.
2. Raman spectroscopy (or other cell growth evaluation method) collects molecular profiles (or other metric) of the sample at t=0.
3. Cartridge/sample is incubated for 2 hours or so.
4. Growth metric is collected once more at t=end.
5. Client machine reports probabilities of resistances to user or a minimum inhibitory concentration (MIC).
6. Data is stored as a blockchain report on the client machine.
7. If client machine is connected to a server, blockchain report is forwarded for species identification processing and inclusion to the interactive spatial-temporal map. If client machine is not connected to a server, blockchain report will continue to be appended and will be forwarded upon reconnection.

### If you would like to contribute to, offer advice for, or support this project, feel free to contact me. I am not interested in spinning this into a startup that becomes indebted to venture capitalists or other funding sources.
