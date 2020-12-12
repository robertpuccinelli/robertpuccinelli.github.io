---
layout: single
title:  "Build Your Own: Microarray Printer"
excerpt: "A DIY alternative to commercial microarray solutions to reduce equipment costs and enhance throughput. Based on the DeRisi style microarrayer."
category: build
tags: [build, electronics]
comments: true

toc: true
toc_sticky: true

introduction:
  - image_path: /assets/images/posts/170704_CapturedDNA.PNG
    url: "/assets/images/posts/170704_CapturedDNA.PNG"
    excerpt: Small protein spots captures various DNA sequences from solubilized microarray.

arrayer:
  - image_path: /assets/images/posts/170704_Arrayer1.jpg
    url: "/assets/images/posts/170704_Arrayer1.jpg"
    excerpt: "View 1."
  - image_path: /assets/images/posts/170704_Arrayer2.jpg
    url: "/assets/images/posts/170704_Arrayer2.jpg"
    excerpt: "View 2."
  - image_path: /assets/images/posts/170704_Arrayer3.jpg
    url: "/assets/images/posts/170704_Arrayer3.jpg"
    excerpt: "Before slide platter and pin arms."
  - image_path: /assets/images/posts/170704_ArrayerPins.jpg
    url: "/assets/images/posts/170704_ArrayerPins.jpg"
    excerpt: "Silicon microarray pins formerly employed by the DeRisi lab."
  - image_path: /assets/images/posts/170704_ServoControllers.jpg
    url: "/assets/images/posts/170704_ServoControllers.jpg"
    excerpt: "Axes are powered and controlled by servo controllers."

software:
  - image_path: /assets/images/posts/170704_Win98.jpg
    excerpt: "A bit outdated."
    url: "/assets/images/posts/170704_Win98.jpg"
  - image_path: /assets/images/posts/170704_DeRisiArrayMaker.png
    excerpt: "Software pulled from cached site."
    url: "/assets/images/posts/170704_DeRisiArrayMaker.png"
  - image_path: /assets/images/posts/170704_ArrayMaker.png
    excerpt: "ArrayMaker screenshot."
    url: "/assets/images/posts/170704_ArrayMaker.png"
  - image_path: /assets/images/posts/170704_DMC18x2.jpg
    excerpt: "Galil programming reference."
    url: "/assets/images/posts/170704_DMC18x2.jpg"
  - image_path: /assets/images/posts/170704_Gemini.jpg
    excerpt: "Gemini servo reference."
    url: "/assets/images/posts/170704_Gemini.jpg"

CAD:
  - image_path: /assets/images/posts/170704_Arrayer_BlockBody_Solid.png
    excerpt: Pin block body - solid.
    url: "/assets/images/posts/170704_Arrayer_BlockBody_Solid.png"
  - image_path: /assets/images/posts/170704_Arrayer_BlockBody_Xray.png
    excerpt: Pin block body - X-ray.
    url: "/assets/images/posts/170704_Arrayer_BlockBody_Xray.png"
  - image_path: /assets/images/posts/170704_Arrayer_BlockHead.png
    excerpt: Head for block body.
    url: "/assets/images/posts/170704_Arrayer_BlockHead.png"
  - image_path: /assets/images/posts/170704_Arrayer_PrintingArm.png
    excerpt: Printing arm.
    url: "/assets/images/posts/170704_Arrayer_PrintingArm.png"
  - image_path: /assets/images/posts/170704_Arrayer_CalibratorArm.png
    excerpt: Calibrator arm.
    url: "/assets/images/posts/170704_Arrayer_CalibratorArm.png"
  - image_path: /assets/images/posts/170704_Arrayer_CalibratorMount.png
    excerpt: Calibrator mount.
    url: "/assets/images/posts/170704_Arrayer_CalibratorMount.png"
  - image_path: /assets/images/posts/170704_Arrayer_DelrinBlock.png
    excerpt: Delrin block.
    url: "/assets/images/posts/170704_Arrayer_DelrinBlock.png"
---

{% include figure image_path="/assets/images/posts/170704_CapturedDNA.png" caption="Small protein spots capture various fluorescent DNA sequences from a solubilized microarray." %} {: .align-center .width-75}

**PURPOSE:**  
<br>
Provide a DIY alternative to expensive commercial microarray solutions. Benefits of this system include high-throughput spotting and microarray customizability. It was initially built and documented by Joe DeRisi and team back in the late 90's. One of these machines was assembled for the Fordyce lab at Stanford in 2016 and is documented here for others.
{: .notice--info}


## Introduction

As per Wikipedia:

> A microarray is a multiplex lab-on-a-chip. It is a 2D array on a solid substrate (usually a glass slide or silicon thin-film cell) that assays large amounts of biological material using high-throughput screening miniaturized, multiplexed and parallel processing and detection methods.

In essence, if you want to do a high-throughput study with proteins, DNA, or other molecules, there's a possibility that a microarray could fit your needs. In my opinion, the most significant advantage of using microarrays is being able to correlate a spatial signal to a known agent. It should also be noted that microarrays have been slowly phased out over the years due to advances in other technologies, but they still hold niche roles in science and medicine.

The microarray golden era was somewhat before my time, so I don't know many details of how it rose and fell. From what I understand though, microarrays and microarrayers were solely a commercial product that were sold at somewhat exorbitant prices with limited customizability in the 90's. Joe DeRisi worked with a few others in Pat Brown's lab at Stanford to make an open-source system that could be replicated by other labs at a fraction of the price. They created a manual for assembly and developed software to operate the machine, which several groups used for their own systems. Given that many microarrays were nucleic acid based (ie the ViroChip), the use of these systems declined as alternative technologies such as sequencing and digital PCR became more prominent. For some time, I was fortunate enough to be able to operate Joe's microarrayer at UCSF before it was disassembled and had the opportunity to construct one of the machines for the Fordyce lab at Stanford. Since most of the assembly material has been written previously, I'll either be posting the original material, filling in some missing information or providing files that I created to supplement the existing material.

The microarrayer presented here has quite a few advantages and disadvantages that need to be considered before assembling. The greatest disadvantage by far is the sheer size of the machine. It sits on a large vibration-dampening table that's about 6 feet wide and 4 feet long. In addition to that, it will need to be operated in a humidified environment in order to produce respectable arrays. (This latter constraint is eased by using droplet dispensers.) Traditionally, this environment was either a dedicated microarrayer room or a series of tarps hung from the ceiling. To control humidity, 3 or 4 large humidifiers were run throughout the print to maintain ~65% relative humidity. On the other hand, benefits include the ability to handle any full-skirt 384 plates, ability to handle any pins for spotting arrays, ability to print 30,000 spots on 261 slides in 20 hours, and flexibility in programming the arrays. In terms of throughput and customizability, it's hard to beat. In terms of required spacing between spots, the limiting factor will be how large the pins spot the glass slide. Once the axes have been warmed up, the linear encoders prove to be very accurate.

### Short Demo Video

The following video shows the print head printing spots onto 2x3 inch glass slides. In this example, the arrayer:

1. Cleans the pins and returns to the source plate for the next set of samples.
2. Draws samples from (4) adjacent wells on a 384 well plate.
3. Prints (4) replicates of the samples on two regions of the glass slide.
4. Advances to the next slide until all slides are arrayed.
5. Returns to the cleaning station.

<iframe width="210" height="150" src="https://www.youtube.com/embed/TOcTtWNRr2k" frameborder="0" allowfullscreen></iframe>

## Microarrayer Assembly

{% include feature_row id="arrayer" %}

For assembling the machine, there are no resources better than the [M-Guide](#MGuide), which was produced and revised by DeRisi's team. Nearly every detail is covered - such as how to wire all of the axes or build the dust cover to protect the slides during a print. In the early 2000s, the whole build (including parts and tools) cost about $43,000, which was a fraction of the price of other options at the time. Since then, the price for the materials or commercial options have fallen. Maybe it was just luck, but I was able to find a nearly complete DeRisi style microarrayer selling for $4,000 at the time of writing this post.

I won't go into detail about how to assemble it because it has already been written so well. However, I do want to note that some custom parts that I designed for the calibration arm or printing arm and printing block can be found in the [Parts List and Files](#CAD) section below. Not listed there is information on how to make the slide platter. It may be best to contact Joe for that information, but it includes some specialized boring techniques that most machine shops don't have from what I understand.

## Microarrayer Software

{% include feature_row id="software" %}

Unless you happen to have a PC happily running Windows 98, it might be best to not dwell here. Although the DeRisi group did produce software to control the microarrayer, it has aged and it might be best to rewrite a program for yourself. The ArrayMaker software and operating manual was pulled from an archived version of Joe's website and can be found in the [Parts List and Files](#software) section below. This software isn't the latest version (2.78), but it could still prove to be a useful resource regardless. Possibly, the most important thing to note here is that most of the instructions programmed will either be for the Galil DMC-18x2 motion control card or the Gemini servo controllers. Images of their reference guide are posted above.

## Parts List and Files



### Guides

[DeRisi M-Guide](/assets/pdfs/DeRisi_MGuide.pdf) <a name="MGuide"></a>  
[DeRisi Printing Guide](/assets/pdfs/DeRisi_ArrayerPrinting.pdf)  
[Puccinelli Printing Guide](/assets/pdfs/Puccinelli_ArrayerPrinting.pdf)
<a name="software"></a>
### Software

As mentioned previously, the control software produced by the DeRisi group is out-of-date and is listed here for reference only or if you happen to have a functioning Windows 98 computer.

[ArrayMaker v2.60](/assets/software/DeRisi_ArrayMaker_v260.zip)
<a name="CAD"></a>
### Arrayer CAD Files

Provided here are a series of custom parts that I designed to set up the arrayer at Stanford. These are virtually identical to the parts that were used by the DeRisi lab.

[Download AutoCAD and SolidWorks drawings here!](/assets/CAD/170704_ArrayerParts.zip)

{% include feature_row id="CAD" %}

### Arrayer CAD Notes

Some things to note that might not be obvious from the design files:

**Pin Block Body**
* Will need some 1.5mm dowels press fit in the top and lower inner lip to support the colimiter plates that align the silicon pins.
* Will need (4) 2.5mm diameter x 5mm length magnets press fit into the bottom to mount the magnetic plate that holds the lower colimiter plate.
* Will need top (4) holes tapped for M2 to mount the head.
* Will need back (2) holes tapped for M6 to mount to printing arm.

**Pin Block Head**
* Will need a soft and compressible foam cushion that fills the void between the pins and the head. This cushion protects the pins from vibrations and acts as a spring to ensure contact with the glass slide while printing.

**Colimiter Plates**
* Will be fairly expensive to machine due to the size of the features and the tight tolerances. These were initially designed to work with the [Parallel Synthesis Technologies](http://www.parallel-synthesis.com/smt-info.htm) SMT pins, but may be compatible with others.

**Printing Arm**
* Attaches the pin block body to the z-axis.

**Calibrator Arm**
* Attaches the calibrating pin and mechanical switch to the z-axis.
* Will need to be tapped for M2 to attach the calibrator mount.

**Calibrator Mount**
* Attaches the mechanical switch to the calibrator arm.
* Will need to be tapped for M2 to attach the mechanical switch.

**Delrin Block**
* Couples the slide platter to the x-axis.
* Will need to be tapped for M6 for the holes that don't attach to the x-axis.
