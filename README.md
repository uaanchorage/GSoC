# Alaska: Google Summer of Code (GSoC) 
<img src="https://raw.githubusercontent.com/uaanchorage/GSoC/main/figures/Alaska.png" width="150" height="150" align="left" style="padding:10px;"/> 2025 will be our second time participating in the Google Summer of Code (GSoC) as a mentoring organization, and we are already excited about the potential and opportunities. We had four enthusiastic contributors as a [first-time organization in 2024](https://github.com/uaanchorage/GSoC/tree/GSoC-2024). We consist of stable open-source projects in production use in research and relatively young projects. We also have mentors who have participated in several GSoC instances over the past several years and have been active in open-source software development for decades.

We represent the 49th state, Alaska. Anchorage, the largest city in Alaska, has a vibrant open-source community. Through this GSoC initiative, industrial experts that are part of [Alaska Developer Alliance](https://www.akdevalliance.com/) and faculty and researchers from the [University of Alaska Anchorage (UAA)](https://www.uaa.alaska.edu/) and [University of Alaska Fairbanks (UAF)](https://www.uaf.edu/) join hands, to provide a perfect mentoring experience for interested contributors globally. We provide a glimpse of this northern state and its tech landscape to the Lower 48 and the outside world through this open-source remote summer coding program organized and funded by Google. Our projects focus on healthcare, climate science, polar science, and other research fields critical to the Circumpolar North and the rest of the world.

**Please first refer to the [contributor guidelines](/CONTRIBUTOR-GUIDE.md) to get started!** It puts you on the right track with application details and a standard template. **Please also refer to our [Acceptable and Ethical AI Use Policy](/Acceptable-and-Ethical-AI-Use-Policy.md) to make sure your use of AI/ML/LLM tools such as ChatGPT falls under the acceptable use.** A [rubrics](/Rubrics.md) is provided as reference material on being a competitive applicant for Alaska in GSoC.

**Please avoid sending individual private emails (or social media messages!!) to mentors.** However, the mentors' emails with each project idea are listed below in case the mentor initiates or recommends an email communication later. If you are proposing your own idea, make sure that idea is relevant to Alaska and has a potential mentor from the list of mentors below.

# Project Ideas
Many of the ideas proposed here have a research component. Contributors who work on these ideas have the potential to author a research paper (as the first author, working with the researchers from the University of Alaska) or become co-authors in our ongoing research papers. We strongly encourage those interested in higher studies or research careers to apply for their GSoC with us.

***

**[1] Automated coastline extraction for erosion modeling in Alaska.**

**Mentors:** Frank Witmer (fwitmer -at- alaska.edu) and Rawan Elframawy (rawann.elframawy -at- gmail.com)

**Overview:** The rapidly warming Arctic is leading to increased rates of coastal erosion, placing hundreds of Alaska communities at the frontline of climate change. Understanding current rates of coastline change and accurately forecasting future changes is critical for communities to mitigate and adapt to these changes. Current modeling approaches typically use a simple linear model based solely on historical coastline positions to measure rates of change and extrapolate them into the future. In doing so, these models fail to capture the dynamic effects associated with decreasing sea ice, increasing annual wave energy, and increasing temperatures. To improve the quality of these coastal models, we need to increase the quantity of digitized coastlines, but manual photointerpretation is slow and laborious.

**Current Status:** An initial model and pipeline have been developed to automatically extract coastlines from [PlanetLabs imagery](https://www.planet.com/). An auto-download script is available to retrieve PlanetLabs imagery (3-5m spatial resolution) by specifying any timeframe, cloud coverage percentage, and geometry. Additionally, [NDWI](https://en.wikipedia.org/wiki/Normalized_difference_water_index) with a majority sliding window has been introduced, allowing a specific threshold for each window to improve water detection accuracy. The [DeepWaterMap](https://github.com/isikdogan/deepwatermap) algorithm was originally trained with the [Global Surface Water (GSW)](https://developers.google.com/earth-engine/datasets/catalog/JRC_GSW1_4_GlobalSurfaceWater) dataset at 30 m resolution from [Landsat](https://landsat.gsfc.nasa.gov/) imagery, but the model did not not work well applied to PlanetLabs imagery. We are working to re-train the model using PlanetLabs imagery automatically labeled using the NDWI thresholding method. This project extends and expands on the progress made in 2024.

_Potential areas of improvement:_
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

**Difficulty Level:** Medium

***



**[2] Support for Logarithmic Number Systems in a Deep-Learning Framework.**

**Mentors:** Mark Arnold (markgarnold -at- yahoo.com) and Ed Chester (ed.chester -at- gmail.com)

**Overview:** The Logarithmic Number System (LNS) is an alternative to built-in Floating Point (FP), which makes multiplication and division easy at the expense of more difficult addition. Using overloaded operators, xlns provides an open-source Python library for LNS arithmetic. Interest in fabricating LNS hardware has grown since it may reduce power consumption for applications that tolerate approximate results, such as deep learning (see [1]-[5]).  The problem is deep learning often relies on open-source Python frameworks (like Tensorflow or Pytorch) that are hardcoded to use FP hardware. A key feature of these frameworks is the ability to automatically compute gradients (based on the chain rule) by recording extra information about the computation stored in FP format. Such gradients are used during backpropagation training to update network weights. 

**Current Status:** xlns, Tensorflow and Pytorch are all interoperable with the widely-used open-source Numpy library, but xlns is not interoperable with the Tensorflow and Pytorch frameworks because both frameworks are hard coded to use built-in int or FP data internally instead of LNS. 

**Expected Outcomes:** The goal of this project is to provide support for a deep learning framework that uses xlns instead of FP internally (including network specification, automatic gradient, forward inference, and back-propagation training) while keeping high-level compatibility with the framework.  This might be as part of xlns, or as a forked version of the chosen framework, or both.  The contributor may choose either Pytorch or Tensorflow.  The contributor should justify these decisions as part of the proposed design.

**Required Skills:** Calculus, Python, Numpy, and either Pytorch or Tensorflow


**Code Challenge:** The following three challenges illustrate the breath of issues involved.  Each involves only a few lines of Python.  Each involves working with both xlns and the framework.  Doing all three in both Tensorflow and Pytorch might give evidence for which framework is more likely to lead to the expected outcome.

 1) Currently, when the data starts in xlns format, Pytorch/Tensorflow converts to FP. As part of the code challenge, we expect the contributor to provide short Python code snippets that demonstrate that if the data starts in xlns format, the computation cannot be carried out in the xlns format.
    
 2) xlns/examples/arn_generic.py is a hard-coded illustration of training a fully connected MLP with 28*28 input nodes, 100 hidden nodes and 10 output nodes using MNIST digit set.  The hidden layer uses RELU and the output layer uses softmax.  The FP weights for this are initialized as: 
````
W1 = np.array((list(np.random.normal(0, 0.1, (785, 100)))))                    
W2 = np.array((list(np.random.normal(0, 0.1, (101, 10)))))
````
Because there is an extra weight for a constant 1.0 input in each layer, the number of rows is one larger than the inputs to the layer.  The example can be run with various data types, for example with xlnsnp (LNS internally implemented with int64 Numpy ufuncs):
````
python3 arn_generic.py --type xlnsnp --num_epoch 7
````
or more conventionally
````
python3 arn_generic.py --type float --num_epoch 7
````
The code challenge is to implement a similar size fully connected network (in FP) using the provided features of Pytorch or Tensorflow and compare its convergence with arn_generic.py (Note: arn_generic.py uses manual differentiation, ie, the derivative of RELU is a constant, which depends on the sign of the argument, and elementary backpropagation implements the chain rule).

3) Consider LNS addition (1+2=3 and 3-1=2). The following illustrates the overloaded operator and xlnsnp internal representation (sign is LSB of the int64 value; the log portion is the rest): 
````
>>> import xlns as xl
>>> x=xl.xlnsnp([2.0, 3.0])
>>> x
xlnsnp([xlns(1.9999999986889088) xlns(2.9999999688096786)])
>>> x.nd
array([16777216, 26591258])
````
By default, the log portion here is given with 23 bits of precision (see help for xl.xlnssetF for details on how to lower the precision as would be useful in machine learning), which is why the log(2.0) is given as 16777216.  
````
>>> 2*np.int64(np.log2([2.0, 3.0])*2**23)
array([16777216, 26591258])
````
The expression with log2 double checks the answer for x in 23-bit format (with the additional *2 to make room for the sign bit).  Had the +2.0 been -2.0, the representation would have been 16777217.
````
>>> y=xl.xlnsnp([1.,-1.])
>>> y
xlnsnp([xlns(1.0) xlns(-1.0)])
>>> y.nd
array([0, 1])
````
The above illustrates that the log(1.0)=0, and that the sign bit is one for negative values.
````
>>> x+y
xlnsnp([xlns(2.9999999688096786) xlns(1.9999999986889088)])
>>> (x+y).nd
array([26591258, 16777216])
````
Although the Pytorch/Tensorflow frameworks don’t support LNS, LNS can be constructed from int64 and float operations (which is how xlnsnp works).  In xlns/src/xlns.py, there is a function sbdb_ufunc_ideal(x,y). If you call this with the following code:
````
>>> import numpy as np
>>> def myadd(x,y):  
          return np.maximum(x,y)+xl.sbdb_ufunc_ideal(-np.abs(x//2-y//2), (x^y)&1) ))
````
it performs the same operation internally on int64 values as the overloaded operator: 
````
>>> myadd(x.nd,y.nd)
array([26591258, 16777216])
````
Such operations are supported by the frameworks (rather than here from np).  This code challenge is to do a similar toy example within the tensor types provided by the framework, which gives a small taste of the difficulty involved in this project. (The code above for myadd is a slight oversimplification of ````xl.xlnsnp.__add__;```` see this for details on the treatment of 0.0.) 
 
**References:**

[1] G. Alsuhli, et al., “Number Systems for Deep Neural Network Architectures: A Survey,” https://arxiv.org/abs/2307.05035, 2023. 

[2] M. Arnold, E. Chester, et al., “Training neural nets using only an approximate tableless LNS ALU”.  31st International Conference on Application-specific Systems, Architectures and Processors. IEEE. 2020, pp. 69–72. https://doi.org/10.1109/ASAP49362.2020.00020

[3] O. Kosheleva, et al., “Logarithmic Number System Is Optimal for AI Computations: Theoretical Explanation of Empirical Success”, https://www.cs.utep.edu/vladik/2024/tr24-55.pdf

[4] D. Miyashita, et al., “Convolutional Neural Networks using Logarithmic Data Representation,” https://arxiv.org/abs/1603.01025, Mar 2016.

[5] J. Zhao et al., “LNS-Madam: Low-Precision Training in Logarithmic Number System Using Multiplicative Weight Update,” IEEE Trans. Computers, vol. 71, no. 12, pp.3179–3190, Dec. 2022, https://doi.org/10.1109/TC.2022.3202747

**Source Code:** https://github.com/xlnsresearch/xlns

**Discussion Forum:** https://github.com/xlnsresearch/xlns/discussions

**Effort:** 350 Hours

**Difficulty Level:** Hard

***


**[3] Developing Distributed Algorithm for Metagenomic Error Correction and Assembly.**

**Mentors:** Arghya Kusum Das (akdas -at- alaska.edu) and Yali Wang (ywang35 -at- alaska.edu)

**Overview:** A metagenomics study of Alaska would explore the diverse microbial communities in its unique environments, including the Arctic, marine, and terrestrial ecosystems. Such research could uncover insights into microbial adaptation to extreme conditions and contribute to understanding environmental and climate-related changes in the region. Metagenomic study has an immense impact on multiple science and engineering projects in Alaska such as, arctic healthcare, arctic water pollution, bio leaching on rare earth elements, arctic environmental sustainability and resilience, understanding boreal forest dynamics, wildfire mitigation, and so on. The list is never ending.
Shotgun metagenomics, which involves sequencing DNA from a mixed sample of genomes within a community, offers a high-throughput approach to examine the genomic diversity of microbial populations. A key step in metagenomic analysis is assembling the shotgun reads into longer contiguous sequences, or contigs. However, genome assemblies from short reads are often highly fragmented, potentially generating millions of contigs per sample, especially in diverse communities. This challenge arises due to issues like sequence repeats within and between genomes, low coverage of certain species, and strain variability.

**Current Status:** Because of the variability in abundance in multiple species in the mixed sample of genomes, it is hard to design a theoretically solid algorithm to rectify the error in the sample and assemble it accurately. The low abundance species in the mixed sample are often wrongly classified as error if we use a traditional/existing algorithms that can rectify the error in a single species’ whole genome sequence. For the similar reason, the existing metagenomic assemblers are perform sub-optimally. 
Further, the existing software are limited in terms of their data handling capability. Most of them are capable to operate in a single node only. So, their data nailing is severely limited by the RAM available in one node. Also the time consumed for large datasets are often unreasonable.

**Expected Outcomes:** In this project, we will address the first two steps in metagenomic analysis i.e., error correction and assembly which are paramount for any downstream project. Metagenomic data is often large in size, spanning to hundreds of gigabytes to terabyte scale. Our motivation is to develop distributed, an HPC-compatible solution for metagenomic error correction and assembly.

(1) We are looking for working solutions (a solid algorithm and its implementation) for metagenomic error correction and assembly. The solutions should be theoretically justifiable and/or biologically meaningful. (2) The algorithm and the software implementation for both error correction and assembly should be distributed in nature. (3) We are open for AI/ML-enabled solutions, but that is not a requirement. (4) GPU-enabled solutions are also encouraged but, it’s also not a requirement.

**Required Skills:** Python and experience with Deep Neural Networks

**Code Challenge:** Prior experience creating deep learning models is expected.

**Source Code:** https://github.com/akdasUAF/Metagenome

**Discussion Forum:**  https://github.com/akdasUAF/Metagenome/discussions/

**Effort:** 350 Hours

**Difficulty Level:** Medium/Hard

***

**[4] Telehealth over L4S.**

**Mentors:**  Kolawole Daramola (koladaramola -at- icloud.com) and Pradeeban Kathiravelu (pkathiravelu -at- alaska.edu)

**Overview:** Low Latency, Low Loss, and Scalable Throughput (L4S) Internet Service [1](https://datatracker.ietf.org/doc/rfc9330/), [2](http://www.watersprings.org/pub/id/draft-ietf-tsvwg-l4s-arch-06.html), [3](http://www.ring.gr.jp/archives/doc/RFC/rfc9330.pdf) has shown promising performance, by rethinking congestion control. Can we have a telehealth deployment with pairs of L4S nodes? Perhaps starting with something simple, such as two DICOM endpoints to send radiographic images in between? [Linux kernel with L4S patches](https://github.com/L4STeam/linux) can be a good point to start for the endpoints. How L4S, with telehealth and other applications, as well as classic non-L4S traffic, share the network will be an interesting test. 

**Current Status:** A prototype has been built as part of the GSoC 2024. As rural Alaska is largely unconnected by the road network, people often need to fly into larger towns such as Fairbanks and Anchorage for their healthcare needs. This state of affairs has steered the telehealth initiatives in Alaska much more than elsewhere in the US. Our research partners from healthcare organizations such as [Alaska Native Tribal Health Consortium (ANTHC)](https://www.anthc.org/) utilize telehealth in their daily operations. Improved telehealth access and performance can significantly benefit the patients and providers in terms of patient satisfaction and comfort.

**Expected Outcomes:** This project will review the latest advances from the research, deployment, and testing perspectives with using L4S in telehealth. The contributor will look into how this can be deployed in practice for various telehealth applications – sending DICOM images for diagnostics (high volume of data but tolerance for high latency), telemonitoring via wearable devices (low volume of data but demand for low latency), televisits (a video call through apps such as Zoom – high volume of data and demand for high latency). As a result of this project, we will understand whether we need any optimizations for L4S to use for telehealth applications and potential alternative approaches. 

**Required Skills:** Python

**Code Challenge:** Experience with network protocols and installing Linux servers is a plus. Coding experience demonstrating such experiences is considered positive.

**Source Code:** https://github.com/KathiraveluLab/L4SBOA

**Discussion Forum**: https://github.com/KathiraveluLab/L4SBOA/discussions

**Effort:** 350 Hours

**Difficulty Level:** Hard

***



**[5] Creating shareable "albums" from locally stored DICOM images**

**Mentors:** Ananth Reddy (bananthreddy30 -at- gmail.com) and Pradeeban Kathiravelu (pkathiravelu -at- alaska.edu)

**Overview:**  DICOM data sets downloaded from PACS environments typically remain in the local environments, such as a research server or a cluster where the DICOM retriever (C-MOVE) is run. To use this data, researchers must identify certain subsets of data. This can be achieved by querying the retrieved data. DICOM images consist of textual metadata. By querying the metadata, subsets of images can be identified. However, currently, creating "albums" from locally stored DICOM images is not seamless.

**Current Status:** This feature does not exist in our open-source frameworks. We share images through other orthogonal approaches (via rclone, for example). This project will implement a stand-alone utility to effectively create albums from locally stored DICOM images.

**Expected Outcomes:** Several approaches to implementing such album features exist. One approach is to use [Kheops](https://docs.kheops.online/) to provide an interface to create and view the albums. [MEDIator](https://github.com/sharmalab/MEDIator) can be extended to create subsets and share the images via a unique URL as well. The proposed feature will make the images accessible to more researchers for their experiments by replacing the current manual data sharing efforts. Moreover, Kheops natively integrates with OHIF Viewer. As such, images retrieved locally can be viewed through OHIF Viewer by creating albums with Kheops. Contributors are encouraged to use Kheops or alternatives rather than reinventing the wheel (unless there is a convincing reason).
 
**Required Skills:** Python or Java.

**Code Challenge:** Experience working with DICOM images from previous projects or through a sample dummy project will be a plus.

**Source Code:** https://github.com/KathiraveluLab/Diomede (New Project).

**Discussion Forum**: https://github.com/KathiraveluLab/Diomede/discussions

**Effort:** 350 Hours

**Difficulty Level:** Easy

***


**[6] Beehive: Integrated Community Health Metrics Framework for Behavioral Health to Supplement Healthcare Practice in Alaska.**

**Mentors:** David Moxley (dpmoxley -at- alaska.edu) and Pradeeban Kathiravelu (pkathiravelu -at- alaska.edu)

**Overview:** This project, a collaboration between the University of Alaska Anchorage Departments of Computer Science and Human Services, seeks to create a digital approach to translating the digitalization of art and photographic images into a digital database that stores in retrievable formats those images for use in advancing the delivery of human services and health care to people who experience considerable vulnerability and marginalization within the community. One of the project goals is to create a digital repository of these images, many of which reflect Outsider Art since the people who produce them are not formally trained as artists and experience considerable discrimination. The repository can be used to support research on Outsider art and Outsider Artists, education of health and human services practitioners about the impact of negative stereotypes on the health and well-being of people who are highly vulnerable, and arts programs devoted to advancing the health of vulnerable people.

This project aims to develop [Beehive](https://github.com/KathiraveluLab/Beehive/), a prototype implementation as an open-source data federation framework that can be used in research environments in Alaska and elsewhere.

**Current Status:** A prototype has been built as part of Alaska Season of Code. We are researching the approach for its use with our community partners in Anchorage, aiming to support marginalized folks such as the unhoused.

**Expected Outcomes:** In this project, the contributor will develop the Beehive platform for (1) translating digital images into the database, (2) developing the database to support user interactions with content, and (3) facilitating retrieval of images. The contributor will obtain an orientation to the project, instruction in how the arts and photography can represent health and well-being, and insight into using digital representations as an advocacy tool for improving the well-being of highly vulnerable people. 

**Required Skills:** Database (MySQL or Mongo) and Python or Java. A build management tool such as Apache Maven is recommended if using Java.

**Code Challenge:** Prior experience with database management through established coding examples. Pull requests to Beehive to address open issues are highly encouraged (although not mandatory).

**Source Code:**  https://github.com/kathiraveluLab/beehive.

**Discussion Forum**: https://github.com/KathiraveluLab/Beehive/discussions/

**Effort:** 350 Hours

**Difficulty Level:** Medium

***




**[7] DICOM Image Retrieval and Processing in Matlab.**

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

**[8] Making ZeroMQ a first-class feature of concore.**

**Mentors:** Shivang vijay (shivangvijay -at- gmail.com), Rahul Jagwani (rahuljagwani1012 -at- gmail.com), and Mayuresh Kothare (mvk2 -at- lehigh.edu) 

**Overview:** [concore](https://github.com/ControlCore-Project/concore) is a lightweight framework for closed-loop peripheral neuromodulation control systems. _concore_ consists of a file-sharing based _concore_ protocol to communicate between the programs in a study. _concore_ also allows a shared-memory based communication between programs. This project will implement a [ZeroMQ](https://zeromq.org/)-based communication between programs, as an alternative to the file-sharing based and shared-memory based communications. ZeroMQ is a message-oriented middleware implemented in multiple languages, which natively supports communications across computing nodes. Such an implementation will improve the usability of _concore_ in distributed environments.


![The study with 0MQ](figures/zeromq.png)

**Current Status:** We experimented with an [osparc-control](https://pypi.org/project/osparc-control/0.0.2/) based communication as an alternative to this default file-sharing based concore protocol. [osparc-control](https://github.com/ITISFoundation/osparc-control) is an extension of ZeroMQ. Our experimental osparc-control based implementation replaces the file-sharing mechanism restricted to one local machine with message queues that can be transmitted between locally networked machines. The contributor will use this osparc-control based communication as an inspiration for the proposed ZeroMQ-based implementation, which will function as a first-class approach to implement the edges of concore without using osparc-control. In our current experimental [osparc-control based implementation](https://github.com/ControlCore-Project/concore/tree/main/0mq), these ZeroMQ edges are not visible in the _concore_ editor, the browser-based visual editor for _concore_. Consequently, studies with osparc-control are represented as forests instead of directed hypergraphs due to the "invisible" ZeroMQ communication. This also means to run a concore study with ZeroMQ communication, we have to run each hypergraph in the forest separately.

**Expected Outcomes:** We need to promote a unified experience in concore, whether the edges are implemented via the default file-sharing approach, shared-memory approach, or through this ZeroMQ message-based approach. In the _concore_ file-sharing approach, we label the edges with alphabetical characters. In the _concore_ shared-memory approach, we label the edges starting with positive decimal integers (specifying the memory channels used for the sharing). Therefore, to denote the _concore_ ZeroMQ-based edges, the contributor should assume that all the ZeroMQ-edges must start with "0" in their labels, followed by a hexadecimal port, followed by an underscore (_). For example, edge 0x1234_Y assigns the logical Y to port 1234 and edge 0xabcd_U assigns the logical U to port abcd. Once such a graph with ZeroMQ-edges is made (a single directed hypergraph, rather than a forest with disjoint two or more directed hypergraphs), we should be able to seamlessly build and run the study regardless of the underlying communication mechanism. Thus, we aim to demonstrate the possibility of a seamless local vs. distributed execution in a cluster through ZeroMQ.

As the expected outcome of this project, we propose a ZeroMQ-based communication for _concore_ with Python. In addition, the contributor may also implement the ZeroMQ-based communication with other programming languages supported by _concore_ such as Matlab and C++. The contributor may also get inspiration from how the shared-memory based communication is implemented in _concore_.

**Required Skills:** Python

**Code Challenge:** Prior experience in Python must be demonstrated. Prior experience with message-oriented middleware frameworks such as ZeroMQ can be a plus, although not mandatory. Pull requests to CONTROL-CORE projects to address open issues are encouraged (although not expected).

**Source Code:**  https://github.com/ControlCore-Project/concore

**Discussion Forum**: https://github.com/ControlCore-Project/concore/discussions

**Effort:** 350 Hours

**Difficulty Level:** Medium

***

**[9] Dynamic DICOM Endpoints.**

**Mentors:** Ananth Reddy (bananthreddy30 -at- gmail.com) and Pradeeban Kathiravelu (pkathiravelu -at- alaska.edu)

**Overview:** DICOM (Digital Imaging and Communications in Medicine) is a radiographic imaging standard for how various modalities of scanners, PACS (Picture archiving and communication system), and other imaging systems communicate. As a storage protocol, it defines how images are stored in a standard way. It also functions as a messaging protocol, an extension to TCP. DICOM implementations often have a queue to hold the images sent from the source. Since this is a networking communication, a queue may degrade the performance or introduce data loss. DICOM communications are defined by static source, query, and destination endpoints. Each endpoint is defined by hostname/IP address, port, and AE (Application Entity) Title. A DICOM endpoint, such as a PACS or a scanner, usually has these endpoints statically configured to ensure security and patient privacy.

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


**[10] Bio-Block: A Blockchain-based Data Repository and Payment Portal.**

**Mentors:** Chalinda Weerasinghe (chalindaweerasinghe -at- gmail.com), Erik Zvaigzne (erik.zvaigzne-at-gmail.com), and Forrester Kane Manis (Forrester-at-headword.co) 

**Overview:** Most biological, genomic, genetic, medical, and behavioral data are currently collected, stored, and sold by vendors who initially offer products and services to clients in order to accumulate this data. The data, once given to companies, remains the property of the company, with very little compensation and autonomy offered to customers who provided the data in the first place. Can we create a secure, decentralized, and scalable data repository of such information for humans and animals, a true bio-block available to all and open-sourced, whereby the data owners get directly compensated? This project offers a response in the affirmative and leverages blockchains for data distribution, archiving, recording, and payments using a dual-chain structure on the Ethereum blockchain. 

**Current Status:** This project is currently in the research stage.

**Expected Outcomes:** This overall project will be one of the first offerings of an open-source platform for all biological/medical/genomic/behavioral data that leverages the advantages of blockchains. While proprietary dual-chain blockchain architectures are used by companies in this space, our endeavor, through its sub-projects, aims to proof up the architecture that can be scaled and extended to all forms of client-submitted data and multiple retrieval and payment options.  A proof of concept of the architecture will be tested using multivariate, heterogenous synthetic data. 

**Required Skills:** Python is proposed as the programming language. However, students can also propose their preferred alternative programming language and frameworks. Prior experience developing on Ethereum is a plus. 

**Code Challenge:** Prior experience in Python (or the proposed alternative language) and, preferably, Ethereum blockchain through established coding examples. Students are expected to establish their experience with Blockchain technologies in architecting and programming them through previous projects - ideally through their respective GitHub repository (or similar code repositories).

**Source Code:** https://github.com/bio-block/healthy (New Project).

**Discussion Forum:** https://github.com/bio-block/healthy/discussions 

**Effort:** 350 hours 

**Difficulty Level:** Hard

***


**[11] Adopting Nunaliit for Alaska Native Healthcare Practices.**

**Mentors:** Jessica Ross (jmross2 -at- alaska.edu) and Maria Williams (mdwilliams6 -at- alaska.edu) 

**Overview:** [Nughejagh](https://www.uaa.alaska.edu/academics/college-of-health/departments/human-services/nughejagh-project/index.cshtml) is an Alaska Native holistic healthcare application. It uses [Nunaliit](https://github.com/GCRC/nunaliit) as its map-based interface to store its data. The data is curated from various sources in the form of images, stories, and videos - which are stored using the Nunaliit map-based interface, supported by its CouchDB database. However, currently, Nunaliit lacks several desired features for Nughejagh. This project aims to fill the gap by implementing those features and developing scripts to automate the installation, configuration, and data loading process.

**Current Status:** This project is currently in the research stage.

**Expected Outcomes:** The expected goal is to have Nunaliit fine-tuned and configured to run Nughejagh with all its requirements. The project outcome might be a [new stand-alone repository](https://github.com/Nughejagh/nughejagh) that uses [Nunaliit](http://nunaliit.org/), [a forked version of Nunaliit](https://github.com/Nughejagh/nunaliit), or more likely both.  The contributor should justify their design decisions as part of the proposed design.

**Required Skills:** Prior experience in Javascript, Java, and Python. 

**Code Challenge:** Deploy and configure Nunaliit locally and share a screenshot of a locally-running Nunaliit instance. [Nunaliit runs well on Ubuntu 24.04](https://kkpradeeban.blogspot.com/2024/12/nunaliit-on-ubuntu-2404.html).

**Source Code:** https://github.com/Nughejagh/nughejagh (New Project).

**Discussion Forum:** https://github.com/Nughejagh/nughejagh/discussions 

**Effort:** 350 hours 

**Difficulty Level:** Medium

***

**[12] AWANTA: A Virtual Router based on RIPE Atlas Internet Measurements.**

**Mentors:** Ananth Reddy (bananthreddy30 -at- gmail.com) and Pradeeban Kathiravelu (pkathiravelu -at- alaska.edu)

**Overview:** [RIPE Atlas](https://atlas.ripe.net/) is an Internet Measurement network composed of small network devices, known as RIPE Atlas Probes and Anchors, connected to the participating volunteers' routers. Using RIPE Atlas, we can measure the Internet latency and routing path through ping and traceroute measurements. This project aims to develop a software router that dynamically uses RIPE Atlas measurements to change the scheduling path. Before the implementation of the project, we should study the [existing works](https://ieeexplore.ieee.org/abstract/document/9472847 ) on using RIPE Atlas probe for such network optimization tasks at the Internet scale to quickly understand the state-of-the-art and ensure scientific novelty in our approach. 

**Current Status:** A prototype has been built as part of the GSoC 2024. We observe the use of such a framework in the Circumpolar North. Such an approach can provide significant benefits, especially in Alaska and the Canadian North, where Internet connectivity can be spotty.

**Expected Outcomes:** This project extends the [RIPE Atlas client](https://github.com/RIPE-NCC/ripe-atlas-tools) to use the measurements in network scheduling decisions. First, the measurements should be streamlined to perform periodically across several probes set as sources and destinations. The measurements across several probes in a single city can provide a more generalized measurement for a city rather than restricting to individual changes of any given probe when multiple such probes are available to a given city. Second, we will build a virtual router to use these measurements to dynamically influence the network scheduling decisions across several nodes. As the network performance changes with time, we can observe how the network path changes with time. We have more than 60 million RIPE Atlas credits that we accumulated by hosting a RIPE Atlas probe for the past five years. So, we have sufficient resources for these Internet measurement experiments.
 
**Required Skills:** Python.

**Code Challenge:** Prior experience in Python through established coding examples.

**Source Code:**  https://github.com/KathiraveluLab/AWANTA

**Discussion Forum**: https://github.com/KathiraveluLab/AWANTA/discussions/

**Effort:** 350 Hours

**Difficulty Level:** Medium

***


**[13] Alaska Wildfire Prediction Using Satellite Imagery.**

**Mentors:**  Yali Wang (ywang35 -at- alaska.edu) and Arghya Kusum Das (akdas -at- alaska.edu)

**Overview:** Given Alaska’s unique wildfire patterns, where large-scale fires occur annually in boreal forests, tundra, and remote wilderness, predicting fire-prone areas can help mitigate disasters and optimize resource allocation. The presence of vegetation (fuel) is necessary for a fire, but the determining factors are weather conditions (humidity, wind speed, temperature) and an ignition source (lightning, human activity, etc.).
This project aims to develop a hybrid deep learning model to predict wildfire risk in Alaska by integrating optical, thermal, and synthetic aperture radar (SAR) satellite imagery with ground-based weather data.
Traditional wildfire prediction relies on weather data, historical fire records, and human observations, which can be delayed or inaccurate in remote areas like Alaska. In contrast, satellite imagery provides real-time, high-resolution insights into vegetation health, thermal anomalies, burn severity mapping, soil moisture, fuel dryness, and even cloud-penetrating fire detection.

Satellite choices:

| Satellite | Resolution | Revisit Frequency | Why Use It? |
| ------ | ------ | ------ | ------ |
| Landsat 8 & 9 (NASA/USGS) | 30m (multispectral), 100m (thermal) | 16 days | Tracks pre/post-fire vegetation and burn severity with great detail.|
| Sentinel-2 (ESA) | 10m (RGB, NIR), 20m (SWIR) | 5 days | High-resolution images for fire risk classification and early warnings. |
| MODIS (Terra/Aqua, NASA) | 250m (fire detection), 1km (thermal) | Daily | Provides historical fire perimeters and active fire locations. |
| VIIRS (Suomi NPP & NOAA-20) | 375m (fire detection), 750m (thermal) | Daily | Real-time fire monitoring, capturing active hotspots. |
| Sentinel-1 (ESA) | 5m - 20m | 6-12 days | SAR imaging for vegetation moisture & burned area mapping. |
| ALOS-2 (JAXA) | 10m - 100m | 14 days | L-band SAR for detecting dry fuel and terrain changes. |

Additional ground data sources:

1). ERA5 Climate Reanalysis (ECMWF): Provides historical & real-time temperature, wind, and humidity data.

2). NOAA NWS Weather Data: Near real-time humidity, wind, and temperature.

3). Alaska Fire Service (AFS) Wildfire Data: Historical ignition source data (lightning, human activity).

**Current Status:** This project is currently in the research stage.

**Expected Outcomes:**
This project aims to develop a deep-learning model that predicts wildfire risk in Alaska using a combination of satellite and ground-based weather data. The expected outcome of this project would involve both the dataset preprocessing pipeline and the performance of the developed model. Especially, the dataset preprocessing would include how to process the pre-fire and post-fire images efficiently and integrate the ground-based data with satellite imagery. Expected outcomes include:

Minimum viable product (MVP):

Fire risk classification: Given pre-fire satellite images, the model predicts the probability of a fire occurring within a defined time frame like 1 month, 3 months, or 6 months. The classifications should be "High Fire Risk," "Moderate Risk," or "No Risk."

1) Data pipeline development:

Preprocessing satellite images: Band selection, geospatial cropping, cloud removal (For this step, we are mostly interested in analyzing [Sentinel-2 data](https://dataspace.copernicus.eu/explore-data/data-collections/sentinel-data/sentinel-2));

Synthetic Aperture Radar (SAR) analysis: Extracting fuel moisture & terrain features (For this step, we are mostly interested in extracting information like vegetation density and soil moisture from [Sentinel-1 SAR data](https://dataspace.copernicus.eu/explore-data/data-collections/sentinel-data/sentinel-1));

Time-series weather data integration: Incorporating temperature, wind, and humidity. We have access to past decades of weather data for almost the past 30 years for multiple different places in Alaska.

2) Model training and prediction:

A hybrid model such as CNN-LSTM that analyzes satellite data and time-series weather trends (CNN-LSTM is just an example. We are open to multiple different types of analysis methodology);

A web-based GIS dashboard to visualize fire-prone regions in Alaska;

A report on model performance and fire risk metrics.

**Required Skills:** Python. Experience with deep learning and machine learning.

**Code Challenge:** Experience with multi-band satellite imagery, geospatial data processing (like ArcGIS Pro), and remote sensing.

**Source Code:** [https://github.com/YaliWang2019/AK-Satellite-Imagery-Wildfire-Prediction](https://github.com/YaliWang2019/AK-Satellite-Imagery-Wildfire-Prediction) (New Project)

**Discussion Forum:** [https://github.com/YaliWang2019/AK-Satellite-Imagery-Wildfire-Prediction/discussions](https://github.com/YaliWang2019/AK-Satellite-Imagery-Wildfire-Prediction/discussions)

**Effort:** 350 Hours

**Difficulty Level:** Medium/Hard


***

**[14] Support for Logarithmic Number Systems in Large Language Models.**

**Mentors:** Mark Arnold (markgarnold -at- yahoo.com) 

**Overview:** The Logarithmic Number System (LNS) is an alternative to built-in Floating Point (FP), which makes multiplication and division easy at the expense of more difficult addition. Using overloaded operators, xlnscpp provides an open-source C++ library for both 16- and 32-bit LNS arithmetic. Interest in fabricating LNS hardware has grown since it may reduce power consumption for applications that tolerate approximate results, such as deep learning (see [1]-[5]).  Although LNS has been studied extensively for feed-forward networks, only recently [6] has LNS been considered for Large Language Models (LLMs). 

LLMs consist of two main computations: a) feed-forward neural networks for which LNS has been shown to be useful, and b) an operation known as attention.  The training of an LLM produces weights for both of these computations, which are often quantized to reduce data storage requirements. These quantized weights are reconstructed (usually in either 16- or 32-bit FP) and operated on by vectors of tokens (usually in similar FP format).  

Existing LLM engines, such as the open-source [llama.cpp](https://github.com/ggerganov/llama.cpp), perform vector/matrix/tensor operations (mostly matrix multiply) 
between the FP tokens and the weights (in a variety of formats, not including LNS). 

llama.cpp uses a library called [ggml](https://github.com/ggml-org) to do the actual math. The design of ggml supports a variety of FP hardware, such as CPUs and GPUs.   

**Current Status:** xlnscpp is not supported by llama.cpp or ggml. Weights can be stored in a variety of built-in int or FP formats instead of LNS. Matrix operations are carried out in FP.

**Expected Outcomes:** The goal of this project is to provide support for xlnscpp instead of FP in ggml (and indirectly) llama.com. 
At a minimum, this involves modifying ggml to support a "virtual" LNS "machine" using xlnscpp to perform the actual LNS computation,
but which appears to the calling llama.cpp like another hardware platform, like a GPU.  The storage format of the quantized weights would still be the same, but they would be converted to LNS for computations like attention on LNS-format tokens. It is not expected that the speed would be as fast as if hardware FP were used, although a design that minimizes the slowdown is desirable (for instance, converting to LNS once, and reusing LNS many times, much as data is transferred to GPU memory and reused many times there).  The purpose is a proof of concept that LNS yields valid output from an LLM. The design needs to implement enough ggml features to support an actual LLM, like Deepseek.

**Required Skills:** C++ and some familarity with LLMs 

**Code Challenge:**

1) Run the xlns16test.cpp and xlns32test.cpp examples.

2) Go through the ggml example for 32-bit FP matrix multiplication on CPU (
https://huggingface.co/blog/introduction-to-ggml) which illustrates concepts like:
ggml_backend (the code that does the computation on a GPU or CPU),
ggml_context (a "container" that holds data),
ggml_cgraph: (what computation the backend performs),
ggml_backend_buffer: (hold the data of multiple tensors), and
ggml_backend_buffer_type: (a "memory allocator" connected to each ggml_backend). 
This is quite involved because of the ggml_backend concept.  Such experience will help you design a new ggml_backend for LNS (which your design proposal will describe as running on CPU using xlnscpp).  

3) Write a standalone C++ program that has a function to do 32-bit FP matrix multiply with a main program that prints the FP result. Test it with the same matrix data as the previous ggml example. (Hint: use nested for loops to compute the sum of products that form the matrix product).  

4) Modify this program to include xlns32.cpp (define xlns_ideal first) and perform the internal computation in LNS format. The main program and the signature of the function it calls remain the same (32-bit FP), which requires that the function convert to/from LNS before and after the matrix multiply. (Hint: if you do it properly, the overloaded xlnscpp assignment operator takes care of this automatically.) The sum of products should be computed entirely in LNS (not FP). Notice the numeric results are close to what FP produces.  

5) Modify the program to include xlns16.cpp instead. Notice the numeric results are slightly less accurate (the 16-bit LNS product is stored in the 32-bit FP result).  This illustrates the tradeoff of using reduced precision LNS, which is what we want to experiment with in this project.

These code challenges provide possible insight as to how the LNS-CPU backend your design proposal will describe can "look like" an FP backend to llama.cpp. When data would be transferred to the backend, it is converted to LNS.  When data is transfered back to llama.cpp, it is converted back to 32-bit FP.  This is one idea for this project.  You may incorporate improvements to this concept in your design proposal that considers the features of ggml.  


**References:**

[1] G. Alsuhli, et al., “Number Systems for Deep Neural Network Architectures: A Survey,” https://arxiv.org/abs/2307.05035, 2023. 

[2] M. Arnold, E. Chester, et al., “Training neural nets using only an approximate tableless LNS ALU”.  31st International Conference on Application-specific Systems, Architectures and Processors. IEEE. 2020, pp. 69–72. https://doi.org/10.1109/ASAP49362.2020.00020

[3] O. Kosheleva, et al., “Logarithmic Number System Is Optimal for AI Computations: Theoretical Explanation of Empirical Success”, https://www.cs.utep.edu/vladik/2024/tr24-55.pdf

[4] D. Miyashita, et al., “Convolutional Neural Networks using Logarithmic Data Representation,” https://arxiv.org/abs/1603.01025, Mar 2016.

[5] J. Zhao et al., “LNS-Madam: Low-Precision Training in Logarithmic Number System Using Multiplicative Weight Update,” IEEE Trans. Computers, vol. 71, no. 12, pp.3179–3190, Dec. 2022, https://doi.org/10.1109/TC.2022.3202747

[6] P. Haghi, C. Wu, Z. Azad, Y. Li, A. Gui, Y. Hao, A. Li, and T. T. Geng, “Bridging the Gap Between LLMs and LNS with Dynamic Data Format and Architecture Codesign ,” in 2024 57th IEEE/ACM International Symposium on Microarchitecture (MICRO). Los Alamitos, CA, USA: IEEE Computer Society, Nov. 2024, pp. 1617–1631. https://doi.ieeecomputersociety.org/10.1109/MICRO61859.2024.00118


**Source Code:** https://github.com/xlnsresearch/xlnscpp

**Discussion Forum:** https://github.com/xlnsresearch/xlnscpp/discussions

**Effort:** 350 Hours

**Difficulty Level:** Hard

***

**[15] Time and Ordering in Beehive.**

**Mentors:** Jihye Kwon (jkwon2 -at- alaska.edu), David Moxley (dpmoxley -at- alaska.edu), and Pradeeban Kathiravelu (pkathiravelu -at- alaska.edu).

**Overview:** Beehive was initiated as a collaboration between the University of Alaska Anchorage Departments of Computer Science and Human Services, but grew largely into a software platform through open-source contributions. Beehive seeks to create a digital approach to translating the digitalization of art and photographic images into a digital database that stores in retrievable formats those images for use in advancing the delivery of human services and health care to people who experience considerable vulnerability and marginalization within the community. One of the project goals is to extend the current Beehive software as a repository of photomemories (a 2D projection of 3D spaces) X time. This project aims to extend [Beehive](https://github.com/KathiraveluLab/Beehive/) with these additional capacities and develop data mining algorithms to support this use case of photos as frozen snapshots in an individual's life.

**Current Status:** The current Beehive prototype does not consider the complexities of time and ordering in the use of behavioral patterns and narratives in the journey to recovery.

**Expected Outcomes:** In this project, the contributor will (1) extend the Beehive platform to support time and ordering as attributes across images, (2) develop algorithms to understand the impact of past events through the series of images and their narratives, and (3) implement data mining algorithms that could fetch and understannd evolving narratives around photomemories. 

We see spaces as 3D or 2D if we are referring to geolocations. Photos are 2D projections of a 3D space. There is one dimension that we omit in most of these projections. That is time. Time as a 4th dimension is not entirely new in research and applications. A search on spatiotemporal data and space-time continuum will give you plenty of examples, from climate change to science novels. Time, or more specifically, ordering, is an essential variable in behavior. Don't you wonder how you see places differently just because you have seen the same or something similar before? Where it gets more interesting or challenging (depending on how you see it) is how the time affects the exact location and even those "near" it. When we say "near," it is in terms of data, not necessarily in terms of geographical proximity. Sometimes, it is just a minor change, and the location is the same! In data mining, we call this "near duplicates." A change in the name of a place (can be a city or a restaurant!). Other times, these are two entirely different places. Perhaps, Kivalina has moved over time due to the Arctic Erosion (sadly). But that is still geographical proximity. For instance, your visit to Portugal will influence your visits to other Portuguese-speaking nations (such as Angola and Brazil) because they share a language and culture, although they are oceans apart. On a smaller scale, your experience in a library will impact how you perceive another library in a different location. How do we consider time (or in a more accurate sense, "relative time" or "ordering") in our analysis/perception? This is intertwined as the 4th dimension (or 3rd dimension, if you are already projecting the 3D world into a 2D map/photo). This project aims to understand these complexities in a prototype version over simulated/synthetic data.

**Required Skills:** Database (MySQL or Mongo) and Python or Java. Experience and interest in data mining is a plus.

**Code Challenge:** Prior experience with database management through established coding examples. Pull requests to Beehive to address open issues are highly encouraged (although not mandatory).

**Source Code:**  https://github.com/kathiraveluLab/beehive , https://github.com/KathiraveluLab/DREAMS

**Discussion Forum**: https://github.com/KathiraveluLab/Beehive/discussions/

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

**Difficulty Level:** Easy/Medium/Hard

***
