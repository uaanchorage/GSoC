# Alaska: Google Summer of Code (GSoC) 
This is our first time participating as a mentoring organization in the Google Summer of Code (GSoC) as "Alaska." We consist of stable open-source projects in production use in research and relatively young projects. We also have mentors who have participated in several GSoC instances.

We represent the 49th state, Alaska. Anchorage, the largest city in Alaska, has a vibrant open-source community. Through this GSoC initiative, industrial experts that are part of [Alaska Developer Alliance](https://www.akdevalliance.com/) and faculty and researchers from the [University of Alaska Anchorage (UAA)](https://www.uaa.alaska.edu/) join hands, to provide a perfect mentoring experience for interested students globally. We hope to provide a glimpse of this northern state and its tech landscape to the Lower 48 and the outside world through this summer internship program organized by Google.

# List of Ideas



**[1] Making ZeroMQ a first-class feature of concore.**

**Mentors:** Mark Arnold (markgarnold -at- yahoo.com) and Pradeeban Kathiravelu (pkathiravelu -at- alaska.edu)

**Overview:** [concore](https://github.com/ControlCore-Project/concore) is a lightweight framework for closed-loop peripheral neuromodulation control systems. concore consists of its own file-sharing based _concore_ protocol to communicate between the programs in a study. We have introduced an [osparc-control](https://pypi.org/project/osparc-control/0.0.2/) based communication as an alternative to this default file-sharing based concore protocol. 

[osparc-control](https://github.com/ITISFoundation/osparc-control) is an extension of [ZeroMQ](https://zeromq.org/). osparc-control based implementation replaces the file-sharing mechanism restricted to one local machine with message queues that can be transmitted between locally networked machines. This osparc-control based communication should be promoted as a first-class approach to implement the edges of concore.

![The study with 0MQ](figures/0mq.png)

**Current Status:** Currently, a [simple osparc-control based implementation](https://github.com/ControlCore-Project/concore/tree/main/0mq) exists in concore. However, these ZeroMQ edges are not visible in the concore editor, the browser-based visual editor for the concore. Consequently, studies with ZeroMQ edges are represented as forests instead of directed hypergraphs due to the "invisible" ZeroMQ edges. This also means to run a concore study with ZeroMQ-based edges, we have to run each hypergraph in the forest separately.

**Expected Outcomes:** We need to promote a unified experience in concore, whether the edges are actually implemented via the default file-sharing approach or through this experimental osparc-control/ZeroMQ message-based approach. To illustrate the ZeroMQ-based edges, the contributor can choose to introduce a new assumption that all the ZeroMQ-edges must start with "0" in their labels. Usually, we label the edges with alphabetical characters. Therefore, this is a safe assumption. Once such a graph with ZeroMQ-edges is made (a single directed hypergraph, rather than a forest with disjoint two or more directed hypergraphs), we should be able to seamlessly build and run the study regardless of the underlying communication mechanism. Thus, we aim to demonstrate the possibility of a seamless local vs. distributed execution in a cluster through ZeroMQ.

**Required Skills:** Python

**Code Challenge:** Prior experience in Python must be demonstrated. Prior experience with message-oriented middleware frameworks such as ZeroMQ can be a plus, although not mandatory.

**Source Code:**  https://github.com/ControlCore-Project/concore

**Discussion Forum**: https://github.com/ControlCore-Project/concore/discussions

**Effort:** 350 Hours

**Difficulty Level:** Medium

***

**[2] A Reference Implementation for concore Library in Java or Julia.**

**Mentors:** Mark Arnold (markgarnold -at- yahoo.com) and Mayuresh Kothare (mvk2 -at- lehigh.edu)

**Overview:** [concore](https://github.com/ControlCore-Project/concore) is a lightweight framework for closed-loop peripheral neuromodulation control systems. Currently, it supports implementations of programs in Python, C++, Matlab, Octave, and Verilog. In this project, the contributor will develop a reference implementation of the concore library in Java or Julia.

**Current Status:** We developed the concore library initially in Python and then implemented support for other languages. The contributor will work towards a reference implementation in Java or Julia in this project. The successful completion of this project will expand the user base of concore to include Java/Julia developers.

**Expected Outcomes:** A complete reference implementation of the concore Library in Java or Julia.

**Required Skills:** i) Java or Julia and ii) Python

**Code Challenge:** Demonstration of previous expertise in Java/Julia and Python can be beneficial.
 
**Source Code:**  https://github.com/ControlCore-Project/concore

**Discussion Forum**: https://github.com/ControlCore-Project/concore/discussions

**Effort:** 350 Hours

**Difficulty Level:** Medium

***

**[3] Creating shareable "albums" from locally stored DICOM images**

**Mentors:** Ananth Reddy (bananthreddy30 -at- gmail.com) aand Pradeeban Kathiravelu (pkathiravelu -at- alaska.edu)

**Overview:**  [Niffler](https://github.com/Emory-HITI/Niffler) is a framework to retrieve DICOM images from PACS in real-time as a DICOM stream and retrospectively. Images can be retrieved from a PACS via Niffler in real-time (via the Niffler meta-extraction module) or on-demand (via the Niffler cold-extraction module). However, these downloaded data sets remain in the local environments, such as a research server or a cluster where Niffler is run. To use this data, researchers must identify certain subsets of data. This can be achieved by querying the retrieved data. For instance, Niffler stores the metadata of the data retrieved in real time in a Mongo database. By querying the metadata, subsets of images can be identified. However, currently, Niffler does not possess the ability to create such "albums" from a set of DICOM images retrieved by Niffler and shared with other users.

**Current Status:** Currently, Niffler does not have the ability to select subsets of images or create albums. We are sharing images through other orthogonal approaches (via rclone, for example). This project will implement a stand-alone utility to create albums from locally stored DICOM images effectively.

**Expected Outcomes:** There are several approaches to implementing such album features. One approach is to use [Kheops](https://docs.kheops.online/) to provide an interface to create and view the albums. [MEDIator](https://github.com/sharmalab/MEDIator) can be extended and incorporated into Niffler to create subsets and share the images via a unique URL as well.

The proposed feature will make the images retrieved by Niffler accessible to more researchers for their experiments by replacing the current manual efforts of data sharing. Moreover, Kheops natively integrates with OHIF Viewer. As such, images retrieved by Niffler can be viewed through OHIF Viewer by creating albums with Kheops.

An approach to creating shareable datasets from the DICOM images retrieved by Niffler. It could be adopting existing frameworks such as MEDIator and Kheops and scripts and integration code with those frameworks or an entirely new module to Niffler for this feature. However, contributors are encouraged to use Kheops or alternatives rather than reinventing the wheel (unless there is a convincing reason).
 
**Required Skills:** Python and Java.

**Code Challenge:** Experience working with DICOM images from previous projects or through a sample dummy project will be a plus.

**Source Code:** https://github.com/KathiraveluLab/Diomede (New Project).

**Discussion Forum**: https://github.com/KathiraveluLab/Diomede/discussions

**Effort:** 350 Hours

**Difficulty Level:** Easy

***

Please use the below template to create new project ideas.

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
