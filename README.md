# Alaska: Google Summer of Code (GSoC) 
<img src="https://raw.githubusercontent.com/uaanchorage/GSoC/main/figures/Alaska.png" width="150" height="150" align="left" style="padding:10px;"/> 2027 will be our fourth time participating in the Google Summer of Code (GSoC) as a mentoring organization, and we are already excited about the potential and opportunities. We had four enthusiastic contributors as a [first-time organization in 2024](https://github.com/uaanchorage/GSoC/tree/GSoC-2024) and we doubled in 2025 with our excellent 8 contributors and had 8 more contributors in 2026 as well. We consist of stable open-source projects in production use in research and relatively young projects. We also have mentors who have participated in several GSoC instances over the past several years and have been active in open-source software development for decades.

We represent the 49th state, Alaska. Anchorage, the largest city in Alaska, has a vibrant open-source community. Through this GSoC initiative, researchers from the [University of Alaska Anchorage (UAA)](https://www.uaa.alaska.edu/) and [University of Alaska Fairbanks (UAF)](https://www.uaf.edu/) join hands with the Alaska-based software experts that are part of open-source entities such as [Healthy](https://github.com/healthyinc/) and [Alaska Developer Alliance](https://www.akdevalliance.com/) to provide a perfect mentoring experience for interested contributors globally. We provide a glimpse of this northern state and its tech landscape to the Lower 48 and the outside world through this open-source remote summer coding program organized and funded by Google. Our projects focus on healthcare, climate science, polar science, and other research fields critical to the Circumpolar North and the rest of the world.

**Please first refer to the [contributor guidelines](/CONTRIBUTOR-GUIDE.md) to get started!** It puts you on the right track with application details and a standard template. **Please also refer to our [Acceptable and Ethical AI Use Policy](/Acceptable-and-Ethical-AI-Use-Policy.md) to make sure your use of AI/ML/LLM tools such as ChatGPT falls under the acceptable use.** A [rubrics](/Rubrics.md) is provided as reference material on being a competitive applicant for Alaska in GSoC. **Some [helpful pointers on effective communication](Effective-Communication.md) are also provided.**

**Please avoid sending individual private emails (or social media messages!!) to mentors.** However, the mentors' emails with each project idea are listed below in case the mentor initiates or recommends an email communication later. If you are proposing your own idea, make sure that idea is relevant to Alaska and has a potential mentor from the list of mentors below.

# Project Ideas
Many of the ideas proposed here have a research component. Contributors who work on these ideas have the potential to author a research paper (as the first author, working with the researchers from the University of Alaska) or become co-authors in our ongoing research papers. We strongly encourage those interested in higher studies or research careers to apply for their GSoC with us.


***
**[1] Automated coastline extraction for erosion modeling in Alaska.**

**Mentors:** Frank Witmer (fwitmer -at- alaska.edu) and Ritika Kumari (rkjane333 -at- gmail.com)

**Overview:** The rapidly warming Arctic is leading to increased rates of coastal erosion, placing hundreds of Alaska communities at the frontline of climate change. Understanding current rates of coastline change and accurately forecasting future changes is critical for communities to mitigate and adapt to these changes. Current modeling approaches typically use a simple linear model based solely on historical coastline positions to measure rates of change and extrapolate them into the future. In doing so, these models fail to capture the dynamic effects associated with decreasing sea ice, increasing annual wave energy, and increasing temperatures. To improve the quality of these coastal models, we need to increase the quantity of digitized coastlines, but manual photointerpretation is slow and laborious.

**Current Status:** An initial model and pipeline have been developed to automatically extract coastlines from [PlanetLabs imagery](https://www.planet.com/). An auto-download script is available to retrieve PlanetLabs imagery (3-5m spatial resolution) by specifying any timeframe, cloud coverage percentage, and geometry. Additionally, [NDWI](https://en.wikipedia.org/wiki/Normalized_difference_water_index) with a majority sliding window has been introduced, allowing a specific threshold for each window to improve water detection accuracy. The [DeepWaterMap](https://github.com/isikdogan/deepwatermap) algorithm was originally trained with the [Global Surface Water (GSW)](https://developers.google.com/earth-engine/datasets/catalog/JRC_GSW1_4_GlobalSurfaceWater) dataset at 30 m resolution from [Landsat](https://landsat.gsfc.nasa.gov/) imagery, but the model did not not work well applied to PlanetLabs imagery. We are working to re-train the model using PlanetLabs imagery automatically labeled using the NDWI thresholding method. This project extends and expands on the progress made in 2024 and 2025.

_Potential areas of improvement:_
- Improve training data by incorporating the PlanetLabs Usable Data Mask (UDM) data. 
- Data Expansion (Deering 2017–2019 and Beyond): Currently using data from 2017 to 2019 for Deering; we plan to include more recent data to extend the time series.
- Improved Cliff Area Segmentation: Enhance segmentation performance specifically in steep or cliff-like coastal areas.
- Handling Challenging Conditions: Improve segmentation in regions with water shadows, buildings, satellite artifacts, and other data quality issues.
- SWIR and Elevation Data Integration: Investigate combining short-wave infrared (SWIR) data and elevation data (e.g., DEMs) to further refine segmentation accuracy.


**Expected Outcomes:** A finished model with high accuracy that automatically extracts a vectorized coastline representation from PlanetLabs satellite imagery. Then, the model can be applied to large amounts of imagery to model coastline changes over time.

**Required Skills:** Python 

**Code Challenge:** Experience with multi-band satellite imagery, geospatial data processing, and machine learning.

**Source Code:** https://github.com/fwitmer/CoastlineExtraction

**Discussion Forum:** https://github.com/fwitmer/CoastlineExtraction/discussions

**Effort:** 350 Hours

**Difficulty Level:** Intermediate


***


**[2] Understanding proximity in locations and emotions through digitized memories.**

**Mentors:** Mohamed Abdullah F (abdullahfakrudeen2020 -at- gmail.com) and David P. Moxley (dpmoxley -at- alaska.edu).

**Overview:** The project [DREAMS](https://github.com/KathiraveluLab/DREAMS) looks into how emotions evolve with time and uses the photos as a contributing factor towards the journey of recovery in marginalized folks, such as those battling drug use, alcohol use, or those with serious mental illnesses. This project extends our scope further, to understand how even seemingly unrelated places could be connected. While proximity is usually considered based on geo-coordinates, there can be other factors in determining how two locations are proximate in their digital representation. Taking two photos at the same spot will result in duplicate location or, more likely (due to minor changes in positioning), a near-duplicate location. However, sometimes, these are not the exact locations - rather, similar ones. Perhaps, 1) two different churches, two different police stations, ... 2) same language (two different Portuguese restaurants, ...) 3) same/similar cultures... This project aims to formalize such proximity in DREAMS and how they contribute to the evolving emotions.

**Current Status:** The current DREAMS prototype does not take such elaborate measures of proximity. However, proximity (not just geographically, but based on the multiple dimensions that compose the data) needs to be formalized in DREAMS to understand the emotions attached to a particular place (e.g., this particular church) vs. a specific class of places (e.g., any churches).

**Expected Outcomes:** Complexities of time and ordering in the use of behavioral patterns and narratives, formalizing the representation of proximity in location beyond the geo-coordinates. This project contains a research portion. Several studies have been done on the topic. We should use the existing outcomes to expand our understanding further, while also implementing our findings.

**Required Skills:** Python, digital image processing, and data mining.

**Code Challenge:** Prior digital image processing or data mining experience is beneficial. Establish the experience through prior projects or related code samples.

**Source Code:**  https://github.com/KathiraveluLab/DREAMS

**Discussion Forum**: https://github.com/KathiraveluLab/DREAMS/discussions

**Effort:** 350 Hours

**Difficulty Level:** Intermediate

***



**[3] WATER: Workflow Allocation Towards Edge Resources.**

**Mentors:** Chalinda Weerasinghe (chalindaweerasinghe -at- gmail.com) and Karthik Sathish (karthiksathishjeemain -at- gmail.com) 


**Overview:** This project scopes the cloud and edge landscape to build a hybrid-cloud/multi-cloud environment for healthcare workflows. The healthcare workflows can be executed on healthcare data across multiple nodes, in-cloud, across cloud providers, or in a hybrid edge-to-cloud compute continuum. The workflows can be machine learning (ML) models, artificial intelligence (AI) algorithms, and other pipelines that can be facilitated by open-source frameworks such as [Niffler](https://github.com/Emory-HITI/Niffler) and [CONTROL-CORE](https://github.com/ControlCore-Project/). The goal here is to develop WATER as a unified framework that facilitates workflow allocation towards edge resources, using the research and industry best practices with cutting-edge, cloud, distributed, and decentralized frameworks.

**Current Status:** This project is currently in the research stage.

**Expected Outcomes:** A prototype implementation of the WATER framework and demonstration of decentralized execution with sample workflows. The focus is on building a utility framework and an abstraction that facilitates the edge workflow execution rather than a simple decentralized data storage.

**Required Skills:** Python is proposed as the programming language. However, students can also propose their preferred alternative programming language and frameworks. Prior experience developing on cloud and edge environments is a plus.

**Code Challenge:** Prior experience in Python (or the proposed alternative language) and, preferably, cloud and edge frameworks.

**Source Code:** https://github.com/healthyinc/WATER (New Project).

**Discussion Forum:** https://github.com/healthyinc/WATER/discussions

**Effort:** 350 hours

**Difficulty Level:** Intermediate

***

**[4] Creating shareable "albums" from locally stored DICOM images**

**Mentors:** Ananth Reddy (bananthreddy30 -at- gmail.com) and Pradeeban Kathiravelu (pkathiravelu -at- alaska.edu)

**Overview:**  DICOM data sets downloaded from PACS environments typically remain in the local environments, such as a research server or a cluster where the DICOM retriever (C-MOVE) is run. To use this data, researchers must identify certain subsets of data. This can be achieved by querying the retrieved data. DICOM images consist of textual metadata. By querying the metadata, subsets of images can be identified. However, currently, creating "albums" from locally stored DICOM images is not seamless.

**Current Status:** This feature does not exist in our open-source frameworks. We share images through other orthogonal approaches (via rclone, for example). This project will implement a stand-alone utility to effectively create albums from locally stored DICOM images.

**Expected Outcomes:** Several approaches to implementing such album features exist. One approach is to use [Kheops](https://docs.kheops.online/) to provide an interface to create and view the albums. [MEDIator](https://github.com/sharmalab/MEDIator) can be extended to create subsets and share the images via a unique URL as well. The proposed feature will make the images accessible to more researchers for their experiments by replacing the current manual data sharing efforts. Moreover, Kheops natively integrates with OHIF Viewer. As such, images retrieved locally can be viewed through OHIF Viewer by creating albums with Kheops. Contributors are encouraged to use Kheops or alternatives rather than reinventing the wheel (unless there is a convincing reason).
 
**Required Skills:** Python or Java.

**Code Challenge:** Experience working with DICOM images from previous projects or through a sample dummy project will be a plus.

**Source Code:** https://github.com/KathiraveluLab/Diomede

**Discussion Forum**: https://github.com/KathiraveluLab/Diomede/discussions

**Effort:** 90 Hours

**Difficulty Level:** Easy

***


**[5] Usability enhancements to CONTROL-CORE**

**Mentors:** Rahul Jagwani (rahuljagwani1012 -at- gmail.com) and Mayuresh Kothare (mvk2 -at- lehigh.edu)

**Overview:** [CONTROL-CORE](https://github.com/ControlCore-Project/) is a lightweight framework for closed-loop peripheral neuromodulation control systems. It provides multi-language support for program development in various execution environments, such as Linux, Windows, MacOS, and Docker. Due to its research nature and multi-platform and multi-language support, configuring and using CONTROL-CORE has become more challenging for regular users. Through usability enhancements, both in terms of installation and usage, this project aims at reducing the learning curve surrounding the CONTROL-CORE project.

**Current Status:** CONTROL-CORE is a mature research framework. The successful implementation of this project will make it more user-friendly and allow us to expand on the userbase.

**Expected Outcomes:** Usability enhancements in terms of installation and continuous use across the target platforms and execution environments.

**Required Skills:** Since this is somewhat an open-ended problem, contributors are allowed to use technologies that are suitable to implement installers and configurations. Docker experience, working with operating system installers, and Linux is expected. Python and ReactJS experience is a plus, given the CONTROL-CORE backend is largely implemented in Python, and the front-end (concore-editor) is developed in ReactJS.

**Code Challenge:** Demonstration of experience in CONTROL-CORE through prior contributions is a plus.
 
**Source Code:**  https://github.com/ControlCore-Project/concore

**Discussion Forum**: https://github.com/ControlCore-Project/concore/discussions

**Effort:** 350 Hours

**Difficulty Level:** Medium

***

You are welcome to propose new open-source project ideas, especially those that serve the state of Alaska and its people. Please use the below template to create new project ideas. However, if you are proposing a new project idea as a contributor, make sure they are relevant to Alaska specifically and the circumpolar north in general. Also, contact potential mentors from the above-listed mentors and confirm their interest in your project idea before drafting an entire proposal based on your own idea.


**[N] PROJECT TITLE.**

**Mentors:** FIRSTNAME1 LASTNAME1 (email-address) and FIRSTNAME2 LASTNAME2 (email-address)

**Overview:** 

**Current Status:** 

**Expected Outcomes:**  

**Required Skills:** 

**Code Challenge:** 

**Source Code:**  

**Discussion Forum**: 

**Effort:** 90/175/350 Hours

**Difficulty Level:** Easy/Intermediate/Hard

***
