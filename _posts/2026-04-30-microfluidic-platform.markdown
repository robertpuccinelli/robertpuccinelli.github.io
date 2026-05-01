---
layout: single
title:  "A Standalone, Browser Controlled Microfluidic Automation Platform"
excerpt: "A modernized microfluidic control system."
category: build
tags: [build, electronics]
comments: true
last_modified_at: 2026-04-29T20:20:02-05:00

---
![System View]({{ site.baseurl }}/assets/images/posts/MicrofluidicController/PXL_20260422_215300624.PORTRAIT.ORIGINAL.jpg)
![Annotated PCB]({{ site.baseurl }}/assets/images/posts/MicrofluidicController/PneumaticsPhoto.png)


### Microfluidic control platform preprint:

Coming soon!

### Github repository for plfluidics:
![User Interface]({{ site.baseurl }}/assets/images/posts/MicrofluidicController/Publication_Controller_UI.png)
![Software Architecture]({{ site.baseurl }}/assets/images/posts/MicrofluidicController/Publication_Controller_Figure_SoftwareArchitecture.png)
Python application that was developed to control the microfluidic platform can be found at: [https://github.com/robertpuccinelli/plfluidics](https://github.com/robertpuccinelli/plfluidics)

### Github repository for Yocto build of OS:

The platform does not require a custom OS, but it does help with reproducability issues that arise when dependencies change over time. The resources for building the custom Linux OS that was used to run this platform can be found at: [https://github.com/robertpuccinelli/plfluidics](https://github.com/robertpuccinelli/plfluidic_yocto)

### Github repository for custom PLRD1 solenoid driver PCB:
![Annotated PCB]({{ site.baseurl }}/assets/images/posts/MicrofluidicController/Publication_Controller_PCB.png)
Coming soon!

### Compressed copy of poster:
<iframe 
  src="{{ '/assets/pdfs/Puccinelli_Poster_MicrofluidicController-compressed.pdf' | relative_url }}" 
  width="100%" 
  height="600px">
</iframe>