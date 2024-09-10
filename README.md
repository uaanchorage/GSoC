# Alaska: Google Summer of Code (GSoC) 
<img src="https://raw.githubusercontent.com/uaanchorage/GSoC/main/figures/Alaska.png" width="150" height="150" align="left" style="padding:10px;"/> 2025 will be our second time participating in the Google Summer of Code (GSoC) as a mentoring organization, and we are already excited about the potential and opportunities. As a [first-time organization in 2024](https://github.com/uaanchorage/GSoC/tree/GSoC-2024), we had 4 enthusiastic contributors. We consist of stable open-source projects in production use in research and relatively young projects. We also have mentors who have participated in several GSoC instances over the past several years and are active in open-source software development spanning decades.

We represent the 49th state, Alaska. Anchorage, the largest city in Alaska, has a vibrant open-source community. Through this GSoC initiative, industrial experts that are part of [Alaska Developer Alliance](https://www.akdevalliance.com/) and faculty and researchers from the [University of Alaska Anchorage (UAA)](https://www.uaa.alaska.edu/) and [University of Alaska Fairbanks (UAF)](https://www.uaf.edu/) join hands, to provide a perfect mentoring experience for interested contributors globally. We provide a glimpse of this northern state and its tech landscape to the Lower 48 and the outside world through this open-source remote summer coding program organized and funded by Google. Our projects focus on healthcare, climate science, polar science, and other research fields critical to the Circumpolar North and the rest of the world.

**Please first refer to the [contributor guidelines](/CONTRIBUTOR-GUIDE.md) to get started!** It puts you on the right track with application details and a standard application template. 

**Please avoid sending individual private emails (or social media messages!!) to mentors.** However, the mentors' emails are listed below with each project idea in case the mentor initiated or recommended an email communication later. 

# Project Ideas
Many of the ideas proposed here have a research component. Contributors who work on these ideas have the potential to author a research paper (as the first author, working with the researchers from the University of Alaska) or become co-authors in our ongoing research papers. We strongly encourage those interested in higher studies or research careers to apply for their GSoC with us.


**[1] Dynamic DICOM Endpoints.**

**Mentors:** Ananth Reddy (bananthreddy30 -at- gmail.com) and Pradeeban Kathiravelu (pkathiravelu -at- alaska.edu)

**Overview:** DICOM (Digital Imaging and Communications in Medicine) is a radiographic imaging standard for how various modalities of scanners, PACS (Picture archiving and communication system), and other imaging systems communicate. As a storage protocol, it defines how images are stored in a standard way. It also functions as a messaging protocol, an extension to TCP. DICOM implementations often have a queue to hold the images sent from the source. Since this is a networking communication, a queue may degrade the performance or introduce data loss. DICOM communications are defined by static source, query, and destination endpoints. Each endpoint is defined by hostname/IP address, port, and AE (Application Entity) Title. A DICOM endpoint such as a PACS or a scanner usually has these endpoints statically configured to ensure security and patient privacy.

This project attempts to send data from a source to dynamic destinations based on the queue and the performance. This can be a use case for teleradiology with multiple remote healthcare/radiologist sites present or a potential framework to enable federated learning on radiographic images. [Orthanc](https://www.orthanc-server.com/) can be set up as a DICOM endpoint that mimics a PACS [1](https://github.com/Emory-HITI/Niffler/tree/master/modules/cold-extraction). With multiple Orthanc servers configured, such a federated deployment can be prototyped. Ultimately, this project aims to study the possibilities and opportunities of supporting dynamic DICOM endpoints in practice. 

**Current Status:** This project is currently in the research stage.

**Expected Outcomes:** A prototype implementation that supports dynamic DICOM endpoints.

**Required Skills:** Python

**Code Challenge:** Experience working with DICOM images from previous projects or through a sample dummy project will be a plus.

**Source Code:** https://github.com/KathiraveluLab/Diomede (New Project).

**Discussion Forum**: https://github.com/KathiraveluLab/Diomede/discussions

**Effort:** 350 Hours

**Difficulty Level:** Hard

***

**[2] Creating shareable "albums" from locally stored DICOM images**

**Mentors:** Ananth Reddy (bananthreddy30 -at- gmail.com) and Pradeeban Kathiravelu (pkathiravelu -at- alaska.edu)

**Overview:**  DICOM data sets downloaded from PACS environments typically remain in the local environments, such as a research server or a cluster where the DICOM retriever (C-MOVE) is run. To use this data, researchers must identify certain subsets of data. This can be achieved by querying the retrieved data. DICOM images consist of textual metadata. By querying the metadata, subsets of images can be identified. However, currently, creating "albums" from locally stored DICOM images is not seamless.

**Current Status:** This feature does not exist in our open-source frameworks. We share images through other orthogonal approaches (via rclone, for example). This project will implement a stand-alone utility to effectively create albums from locally stored DICOM images.

**Expected Outcomes:** Several approaches to implementing such album features exist. One approach is to use [Kheops](https://docs.kheops.online/) to provide an interface to create and view the albums. [MEDIator](https://github.com/sharmalab/MEDIator) can be extended to create subsets and share the images via a unique URL as well. The proposed feature will make the images accessible to more researchers for their experiments by replacing the current manual data sharing efforts. Moreover, Kheops natively integrates with OHIF Viewer. As such, images retrieved locally can be viewed through OHIF Viewer by creating albums with Kheops. Contributors are encouraged to use Kheops or alternatives rather than reinventing the wheel (unless there is a convincing reason).
 
**Required Skills:** Python and Java.

**Code Challenge:** Experience working with DICOM images from previous projects or through a sample dummy project will be a plus.

**Source Code:** https://github.com/KathiraveluLab/Diomede (New Project).

**Discussion Forum**: https://github.com/KathiraveluLab/Diomede/discussions

**Effort:** 350 Hours

**Difficulty Level:** Easy

***


**[3] Beehive: Integrated Community Health Metrics Framework for Behavioral Health to Supplement Healthcare Practice in Alaska.**

**Mentors:** Pradeeban Kathiravelu (pkathiravelu -at- alaska.edu) and David Moxley (dpmoxley -at- alaska.edu)

**Overview:** This project, a collaboration between the University of Alaska Anchorage Departments of Computer Science and Human Services, seeks to create a digital approach to translating the digitalization of art and photographic images into a digital database that stores in retrievable formats those images for use in advancing the delivery of human services and health care to people who experience considerable vulnerability and marginalization within the community. One of the project goals is to create a digital repository of these images, many of which reflect Outsider Art since the people who produce them are not formally trained as artists and experience considerable discrimination. The repository can be used to support research on Outsider art and Outsider Artists, education of health and human services practitioners about the impact of negative stereotypes on the health and well-being of people who are highly vulnerable, and arts programs devoted to advancing the health of vulnerable people.

This project aims to develop [Beehive](https://github.com/KathiraveluLab/Beehive/), a prototype implementation as an open-source data federation framework that can be used in research environments in Alaska and elsewhere.

**Current Status:** This project is currently in the research stage. We are researching the approach for its use with our community partners in Anchorage, aiming to support marginalized folks such as the unhoused.

**Expected Outcomes:** In this project, the contributor will develop the Beehive platform for (1) translating digital images into the database, (2) developing the database to support user interactions with content, and (3) facilitating retrieval of images. The contributor will obtain an orientation to the project, instruction in how the arts and photography can represent health and well-being, and insight into using digital representations as an advocacy tool for improving the well-being of highly vulnerable people. 

**Required Skills:** Database (MySQL or Mongo) and Python or Java. A build management tool such as Apache Maven is recommended if using Java.

**Code Challenge:** Prior experience with database management through established coding examples.

**Source Code:**  https://github.com/kathiraveluLab/beehive (New Project).

**Discussion Forum**: https://github.com/KathiraveluLab/Beehive/discussions/

**Effort:** 350 Hours

**Difficulty Level:** Medium

***




**[4] DICOM Image Retrieval and Processing in Matlab.**

**Mentors:** Ananth Reddy (bananthreddy30 -at- gmail.com) and Pradeeban Kathiravelu (pkathiravelu -at- alaska.edu)

**Overview:** DICOM (Digital Imaging and Communications in Medicine) is a radiographic imaging standard for how various modalities of scanners, PACS (Picture archiving and communication system) and other imaging systems communicate. As a storage protocol, it defines how images are stored in a standard way. It also functions as a messaging protocol, an extension to TCP. 

Many DICOM processing tools exist. They support receiving images from the scanners and PACS to a research cluster in real-time as an imaging stream or on-demand selectively. They also provide means to anonymize the DICOM images to preserve patient privacy, export the DICOM images into a format such as PNG or JPEG, and extract the textual metadata from DICOM files to store it in a CSV file format or a database. Machine learning pipelines cannot be executed in clinical systems such as scanners and PACS. Therefore, the DICOM images and their metadata in the research clusters can be used to run machine learning pipelines. 

Matlab has some out-of-the-box support for certain DICOM functions, and it could make our job easy in certain projects. This facilitates processing the files from the file system [2](https://www.mathworks.com/help/images/dicom-support-in-the-image-processing-toolbox.html). Region-of-Interest is natively supported for DICOM-RT files in Matlab [3](https://www.mathworks.com/help/images/ref/dicomcontours.html). It also supports deep learning on DICOM and NifTi files [4](https://www.mathworks.com/help/deeplearning/ug/preprocess-volumes-for-deep-learning.html). Matlab currently does not support receiving images from DICOM systems such as PACS and Scanners over the network. Matlab used to have functions that utilize the Dicom toolkit to pull images from another server. It was available through Matlab's file exchange at one point called "dicom server connection." This is not publicly available anymore. However, we have the implementation available locally. The code was not recently tested, and therefore, its usability with the latest Matlab versions needs to be confirmed. 

**Current Status:** This project is currently in the research stage.

**Expected Outcomes:** This project aims to create an easy-to-use open-source Matlab DICOM processing framework. We start with processing DICOM images since the current status of the DICOM networking in Matlab is unknown. But we will explore it, if possible and time permitting. Since this is a research project, we should study the existing projects first to avoid re-inventing the wheel. From Google Scholar, we see many processing and pipelines (ROI, deep learning, ...) on DICOM/DICOM-RT have been implemented using Matlab. Regardless of the scientific novelty, we can get an open-source solution to help with further ML stuff using Matlab on the DICOM files. However, we should also observe how this could be a scientific contribution and its merits beyond what is already available. We can use readily available public DICOM data sources to test our implementations, such as [the Cancer Imaging Archive (TCIA)](https://www.cancerimagingarchive.net/), as that avoids having to deal with sensitive patient data with PHI. We will narrow down on a specific research use case to highlight the framework's usage in research.

**Required Skills:** Matlab

**Code Challenge:** Experience working with DICOM images from previous projects and prior experience with Matlab, as demonstrated through code examples, will be a plus.

**Source Code:** https://github.com/KathiraveluLab/Diomede (New Project).

**Discussion Forum**: https://github.com/KathiraveluLab/Diomede/discussions

**Effort:** 350 Hours

**Difficulty Level:** Hard

***


You are welcome to propose new open-source project ideas, especially those that serve the state of Alaska and its people. Please use the below template to create new project ideas. However, if you are proposing a new project idea as a contributor, make sure they are relevant to Alaska specifically and the circumpolar north in general. Also, contact potential mentors and confirm their interest in your project idea before drafting an entire proposal based on your own idea.

***

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

**Difficulty Level:** Easy/Medium/Hard

***
