# Alaska: Google Summer of Code (GSoC) 
<img src="https://raw.githubusercontent.com/uaanchorage/GSoC/main/figures/Alaska.png" width="150" height="150" align="left" style="padding:10px;"/> 2026 will be our third time participating in the Google Summer of Code (GSoC) as a mentoring organization, and we are already excited about the potential and opportunities. We had four enthusiastic contributors as a [first-time organization in 2024](https://github.com/uaanchorage/GSoC/tree/GSoC-2024) and we doubled in 2025 with our excellent 8 contributors. We consist of stable open-source projects in production use in research and relatively young projects. We also have mentors who have participated in several GSoC instances over the past several years and have been active in open-source software development for decades.

We represent the 49th state, Alaska. Anchorage, the largest city in Alaska, has a vibrant open-source community. Through this GSoC initiative, researchers from the [University of Alaska Anchorage (UAA)](https://www.uaa.alaska.edu/) and [University of Alaska Fairbanks (UAF)](https://www.uaf.edu/) join hands with the Alaska-based software experts that are part of open-source entities such as [Healthy](https://github.com/bio-block/healthy) and [Alaska Developer Alliance](https://www.akdevalliance.com/) to provide a perfect mentoring experience for interested contributors globally. We provide a glimpse of this northern state and its tech landscape to the Lower 48 and the outside world through this open-source remote summer coding program organized and funded by Google. Our projects focus on healthcare, climate science, polar science, and other research fields critical to the Circumpolar North and the rest of the world.

**Please first refer to the [contributor guidelines](/CONTRIBUTOR-GUIDE.md) to get started!** It puts you on the right track with application details and a standard template. **Please also refer to our [Acceptable and Ethical AI Use Policy](/Acceptable-and-Ethical-AI-Use-Policy.md) to make sure your use of AI/ML/LLM tools such as ChatGPT falls under the acceptable use.** A [rubrics](/Rubrics.md) is provided as reference material on being a competitive applicant for Alaska in GSoC.

**Please avoid sending individual private emails (or social media messages!!) to mentors.** However, the mentors' emails with each project idea are listed below in case the mentor initiates or recommends an email communication later. If you are proposing your own idea, make sure that idea is relevant to Alaska and has a potential mentor from the list of mentors below.

# Project Ideas
Many of the ideas proposed here have a research component. Contributors who work on these ideas have the potential to author a research paper (as the first author, working with the researchers from the University of Alaska) or become co-authors in our ongoing research papers. We strongly encourage those interested in higher studies or research careers to apply for their GSoC with us.


***
**[1] Automated coastline extraction for erosion modeling in Alaska.**

**Mentors:** Frank Witmer (fwitmer -at- alaska.edu), Rawan Elframawy (rawann.elframawy -at- gmail.com), and Ritika Kumari (rkjane333 -at- gmail.com)

**Overview:** The rapidly warming Arctic is leading to increased rates of coastal erosion, placing hundreds of Alaska communities at the frontline of climate change. Understanding current rates of coastline change and accurately forecasting future changes is critical for communities to mitigate and adapt to these changes. Current modeling approaches typically use a simple linear model based solely on historical coastline positions to measure rates of change and extrapolate them into the future. In doing so, these models fail to capture the dynamic effects associated with decreasing sea ice, increasing annual wave energy, and increasing temperatures. To improve the quality of these coastal models, we need to increase the quantity of digitized coastlines, but manual photointerpretation is slow and laborious.

**Current Status:** An initial model and pipeline have been developed to automatically extract coastlines from [PlanetLabs imagery](https://www.planet.com/). An auto-download script is available to retrieve PlanetLabs imagery (3-5m spatial resolution) by specifying any timeframe, cloud coverage percentage, and geometry. Additionally, [NDWI](https://en.wikipedia.org/wiki/Normalized_difference_water_index) with a majority sliding window has been introduced, allowing a specific threshold for each window to improve water detection accuracy. The [DeepWaterMap](https://github.com/isikdogan/deepwatermap) algorithm was originally trained with the [Global Surface Water (GSW)](https://developers.google.com/earth-engine/datasets/catalog/JRC_GSW1_4_GlobalSurfaceWater) dataset at 30 m resolution from [Landsat](https://landsat.gsfc.nasa.gov/) imagery, but the model did not not work well applied to PlanetLabs imagery. We are working to re-train the model using PlanetLabs imagery automatically labeled using the NDWI thresholding method. This project extends and expands on the progress made in 2024 and 2025.

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

**Difficulty Level:** Intermediate

***

**[2] BHV: Behavioral Health Vault.**

**Mentors:** Mohamed Abdullah F (abdullahfakrudeen2020 -at- gmail.com) and Pradeeban Kathiravelu (pkathiravelu -at- alaska.edu)

**Overview:** The goal of this project is to provide a digitization approach to record the journey of recovery of people with serious mental illnesses, substance-use disorders, and other social determinants affecting well-being. BHV (Behavioral Health Vault) aims to complement traditional Electronic Health Records (EHRs) by storing patient provided images such as photographs, sketches, and scanned drawings along with associated textual narratives, which may be provided directly by patients or recorded by social workers during interviews. BHV is a minimal, Python-based application that enables healthcare networks to store and retrieve patient-provided images. BHV aims to provide them access to upload, view, and edit their own images and narratives. It will provide admin-level access to system administrators, allowing them to view the entire ecosystem, upload images on behalf of users, along with the narrative, edit images on behalf of users, and delete images or narrations on behalf of users or as a moderation action. Importantly, BHV will also include an optional research module integrating a fuzzy logic–based color-emotion association model (inspired by [Color-Emotion Associations in Art: Fuzzy Approach](https://ieeexplore.ieee.org/document/10464290)). This enables researchers to explore correlations between color palettes in user-submitted images and self-reported emotions supporting studies on emotional recovery, addiction patterns, and social determinants of mental health. This user-driven data (images + emotional self-reports) helps researchers study how environmental factors, social contexts, and personal narratives affect mental health. The system is built for participatory behavioral health research, emphasizing accessibility, transparency, and ethical data handling.

**Current Status:** Currently, we have [Beehive](https://github.com/kathiravelulab/beehive) project. However, it has a complex architecture, which has made it a difficult installation for community health clinics that lack the technical expertise. The goal of BHV is to provide the same functionality while minimizing the complex tech stack of Beehive. The eventual goal of BHV is to replace Beehive and be the "Beehive-2.0." 

**Expected Outcomes:** The Behavioral Health Vault (BHV) will deliver a secure yet minimal system designed for ease of use and installation in healthcare and research environments. The signup and login process will be intentionally simple, allowing users to register using a basic email and password combination or Using [Google OAuth](https://support.google.com/googleapi/answer/6158849?hl=en) would be nice, without unnecessary authentication complexity. The platform will prioritize a lightweight, modular architecture that avoids bloat, ensuring that community clinics and behavioral health researchers can deploy the system effortlessly, even with limited technical expertise. To achieve this, BHV will be installable and runnable from a single command, without the need to start separate services for the frontend, backend, and database. Images will be stored efficiently within the local file system, accompanied by a database index that enables fast search and retrieval of user submissions and narratives. The design will follow a privacy by default approach, incorporating appropriate security measures for sensitive data. Documentation will be concise and easy to follow, supported by the system’s inherently minimal design. Additionally, the platform will integrate an optional fuzzy color emotion analysis module to assist researchers in examining user provided images for emotional patterns, thereby expanding the application’s value beyond data storage toward behavioral health research and recovery studies.

BHV will support the option to create a private GitHub repository for each user, where their uploaded images and related metadata will be securely stored in the cloud. Each repository will contain an `img/` directory for images and a global JSON file maintaining essential metadata such as title, description, and image path. Administrators will be added programmatically as collaborators, ensuring they can view, edit, and moderate submissions, while other users repositories remain private and isolated. In addition to GitHub storage, BHV will continue to support a local storage mode as a secondary option for installations preferring offline or self-hosted operation. To maintain data integrity and performance, each uploaded image will be restricted by a configurable file size limit.

Those Private repo will create under the users account.


**Required Skills:** Python, a datastore such as MySQL, Postgresql, SQLite, or MongoDB, and a minimal front-end.

**Code Challenge:** Prior experience with Python and database systems through established project experience, ideally through previous GitHub repositories.

**Source Code:** https://github.com/KathiraveluLab/BHV (New Project).

**Discussion Forum:** https://github.com/KathiraveluLab/BHV/discussions

**Effort:** 350 Hours

**Difficulty Level:** Intermediate

***

**[3] Alaska Wildfire Prediction Using Satellite Imagery.**

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

**Difficulty Level:** Intermediate/Hard


***


**[4] Understanding proximity in locations and emotions through digitized memories.**

**Mentors:** Jihye Kwon (jkwon2 -at- alaska.edu) and Pradeeban Kathiravelu (pkathiravelu -at- alaska.edu).

**Overview:** The project [DREAMS](https://github.com/KathiraveluLab/DREAMS) looks into how emotions evolve with time and uses the photos as a contributing factor towards the journey of recovery in marginalized folks, such as those battling drug use, alcohol use, or those with serious mental illnesses. This project extends our scope further, to understand how even seemingly unrelated places could be connected. While proximity is usually considered based on geo-coordinates, there can be other factors in determining how two locations are proximate in their digital representation. Taking two photos at the same spot will result in duplicate location or, more likely (due to minor changes in positioning), a near-duplicate location. However, sometimes, these are not the exact locations - rather, similar ones. Perhaps, 1) two different churches, two different police stations, ... 2) same language (two different Portuguese restaurants, ...) 3) same/similar cultures... This project aims to formalize such proximity in DREAMS and how they contribute to the evolving emotions.

**Current Status:** The current DREAMS prototype does not take such elaborate measures of proximity. However, proximity (not just geographically, but based on the multiple dimensions that compose the data) needs to be formalized in DREAMS to understand the emotions attached to a particular place (e.g., this particular church) vs. a specific class of places (e.g., any churches).

**Expected Outcomes:** Complexities of time and ordering in the use of behavioral patterns and narratives, formalizing the representation of proximity in location beyond the geo-coordinates. This project contains a research portion. Several studies have been done on the topic. We should use the existing outcomes to expand our understanding further, while also implementing our findings.

**Required Skills:** Python, digital image processing, and data mining.

**Code Challenge:** Prior digital image processing or data mining experience is beneficial. Establish the experience through prior projects or related code samples.

**Source Code:**  https://github.com/KathiraveluLab/DREAMS

**Discussion Forum**: https://github.com/KathiraveluLab/DREAMS/discussions/

**Effort:** 350 Hours

**Difficulty Level:** Intermediate

***


**[5] Building a Decentralized Application (dApp) for Data Analysis in Bio-Block.**

**Mentors:** Chalinda Weerasinghe (chalindaweerasinghe -at- gmail.com), Karthik Sathish (karthiksathishjeemain -at- gmail.com), and Erik Zvaigzne (erik.zvaigzne -at- gmail.com)

**Overview:** The open-source Bio-Block data and payment portal could theoretically admit health and medical information, subject to proper compliance and regulatory protocols. Can we build a dApp that takes this information and performs various levels of analytics: graphical, descriptive, inferential and possibly predictive? What blockchain architectures would permit such a dApp to reside on Bio-Block, and how can we make such a dApp scalable and open? Would the dApp connect through an API, and if so, what would that look like? This project explores and constructs a dApp that meets at least minimal architectural requirements, such as being decentralized, scalable and open, and implements at least two levels of analysis.


**Current Status:**. Bio-Block Healthy App was built as part of the GSoC 2025. This project expands on it to build a decentralized app for data analysis.

**Expected Outcomes:** A dApp that provides data analysis features to Bio-Block.

**Required Skills:** Python is proposed as the programming language. However, students can also propose their preferred alternative programming language and frameworks. Prior experience developing on Ethereum is a plus. 

**Code Challenge:** Prior experience in Python (or the proposed alternative language) and, preferably, Ethereum blockchain through established coding examples. Students are expected to establish their experience with Blockchain technologies in architecting and programming them through previous projects - ideally through their respective GitHub repository (or similar code repositories).

**Source Code:** https://github.com/bio-block/healthy .

**Discussion Forum:** https://github.com/bio-block/healthy/discussions 

**Effort:** 350 hours 

**Difficulty Level:** Intermediate

***


**[6] Anonymization of Personal Health Information (PHI) Submitted to Bio-Block and Improving Data Retrieval.**

**Mentors:** Karthik Sathish (karthiksathishjeemain -at- gmail.com), Ashutosh Ingole (ashingole -at- gmail.com), Forrester Kane Manis (Forrester -at- headword.co).

**Overview:** This is a two-part project. Bio-Block is meant to admit all types of bio-medical information. Some of these data types were explored and tackled in GSoC 2025. The personal health and identification information must be stripped from this data completely so that anonymization is achieved. The first part of the project explores algorithms and processes to completely anonymize the data while maintaining the ability to sort, query and analyze. After anonymization is achieved, there needs to be sufficient ability to query the data so that potential data retrieval is easy and meaningful. The second part of the project entails creating retrieval algorithms and processes to achieve this objective. 

**Current Status:**. . Bio-Block Healthy App was built as part of the GSoC 2025. This project expands on it to build the PHI anonymization pipelines.

**Expected Outcomes:** Data anonymization pipelines built and integrated into bio-block, to remove PHI from data uploads prior to storing those in bio-block.

**Required Skills:** Python is proposed as the programming language. However, students can also propose their preferred alternative programming language and frameworks. Prior experience developing on Ethereum is a plus. 

**Code Challenge:** Prior experience in Python (or the proposed alternative language) and, preferably, Ethereum blockchain through established coding examples. Students are expected to establish their experience with Blockchain technologies in architecting and programming them through previous projects - ideally through their respective GitHub repository (or similar code repositories).

**Source Code:** https://github.com/bio-block/healthy 

**Discussion Forum:** https://github.com/bio-block/healthy/discussions 

**Effort:** 350 hours 

**Difficulty Level:** Intermediate

***





**[7] DICOM Image Retrieval and Processing in MATLAB.**

**Mentors:** Pradeeban Kathiravelu (pkathiravelu -at- alaska.edu) and Ananth Reddy (bananthreddy30 -at- gmail.com)

**Overview:** DICOM (Digital Imaging and Communications in Medicine) is a radiographic imaging standard for how various modalities of scanners, PACS (Picture archiving and communication system), and other imaging systems communicate. As a storage protocol, it defines how images are stored in a standard way. It also functions as a messaging protocol, an extension to TCP. Many DICOM processing tools exist. They support receiving images from the scanners and PACS to a research cluster in real-time as an imaging stream or on-demand, selectively. They also provide means to anonymize the DICOM images to preserve patient privacy, export the DICOM images into a format such as PNG or JPEG, and extract the textual metadata from DICOM files to store it in a CSV file format or a database. Machine learning pipelines cannot be executed in clinical systems such as scanners and PACS. Therefore, the DICOM images and their metadata in the research clusters can be used to run machine learning pipelines. 

MATLAB [Medical Imaging Toolbox](https://www.mathworks.com/products/medical-imaging.html) provides comprehensive support for DICOM using the [DICOM Toolkit (DCMTK)](https://dicom.offis.de/dcmtk.php.en). The MATLAB [Image Processing Toolbox](https://www.mathworks.com/products/image-processing.html) also supports [directly processing DICOM](https://www.mathworks.com/help/images/dicom-support-in-the-image-processing-toolbox.html). Similarly, MATLAB supports [reading, processing, and writing 3-D Medical Images with Spatial Referencing](https://www.mathworks.com/help/medical-imaging/ug/read-process-and-write-3-d-medical-image-with-spatial-referencing.html). In addition, [Python programs can be integrated with MATLAB](https://www.mathworks.com/products/matlab/matlab-and-python.html), which makes it easy to port existing Python workflows into MATLAB incrementally or let them execute interoperably. The out-of-the-box support for DICOM provided by MATLAB could make our job easy in certain projects. This facilitates [processing the files from the file system](https://www.mathworks.com/help/images/dicom-support-in-the-image-processing-toolbox.html). MATLAB natively supports [finding Region-of-Interest for DICOM-RT files](https://www.mathworks.com/help/images/ref/dicomcontours.html). It also supports [deep learning on DICOM and NifTi files](https://www.mathworks.com/help/deeplearning/ug/preprocess-volumes-for-deep-learning.html). 

**Current Status:** This project is currently in the research stage.

**Expected Outcomes:** This project aims to create a MATLAB alternative to the [Niffler](https://github.com/Emory-HITI/Niffler) framework built in Python. Niffler allows real-time and on-demand batch retrieval of DICOM images from the scanners and PACS. It also provides additional features such as metadata extraction, conversion to PNG format, and anonymization. Sample workflows, such as scanner usage computation and IVC filter detection workflows, are included in Niffler. This project is an effort towards building a similar framework, but in MATLAB, using the existing extensive DICOM features provided by MATLAB. We will use MATLAB R2025a for this project. Since this is a research project, we should study the existing projects first to avoid re-inventing the wheel. From Google Scholar, we see many processing and pipelines (ROI, deep learning, ...) on DICOM/DICOM-RT have been implemented using MATLAB. Regardless of the scientific novelty, we can get an open-source solution to help with further ML stuff using MATLAB on the DICOM files. However, we should also observe how this could be a scientific contribution and its merits beyond what is already available. We can use readily available public DICOM data sources to test our implementations, such as [the Cancer Imaging Archive (TCIA)](https://www.cancerimagingarchive.net/), thereby avoiding the handling of sensitive patient data with PHI. We propose using [Orthanc](https://www.orthanc-server.com/), with anonymized DICOM images retrieved from TCIA stored in it, in place of a PACS.

**Required Skills:** MATLAB

**Code Challenge:** Prior experience with MATLAB should be established through previous projects or code samples. Experience working with DICOM images will be a plus.

**Source Code:** https://github.com/KathiraveluLab/DWiM (New Project).

**Discussion Forum**: https://github.com/KathiraveluLab/DWiM/discussions/

**Effort:** 350 Hours

**Difficulty Level:** Intermediate

***


**[8] Support for Logarithmic Number Systems in Large Language Models.**

**Mentors:** Mark Arnold (markgarnold -at- yahoo.com), Alex Krentz (alexkrentz2 -at- gmail.com), and Ed Chester (ed.chester -at- gmail.com)

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


**[9] Telehealth Effectiveness and Necessity Tracker for Alaska.**

**Mentors:** Pradeeban Kathiravelu (pkathiravelu -at- alaska.edu) and David Moxley (dpmoxley -at- alaska.edu).

**Overview:** This project uses public health site data and Internet performance data to find the regions with limited healthcare access (known as the healthcare deserts) but with stable Internet access. The outcome is a web application with a dashboard that can shed light on the necessity and feasibility of telehealth across Alaskan cities and villages.  
 
A compound metric should be defined to identify healthcare deserts, incorporating information such as the number of health sites in the region, the availability of specialist access, the distance to the nearest clinic for any resident, and the presence of a transportation network. Health site data may be retrieved from public sources (such as [https://healthsites.io/map]), but should be supplemented with local sources for accuracy. Internet access and performance can be identified through measurement networks (such as [https://broadbandmapping.com]) and Internet Service Provider (ISP) data. 

A mashup of healthcare access (or the lack of it) combined with Internet access and performance should be visualized as an overlay on the map of Alaska using map platforms such as OpenStreetMap, with interactive visualizations. 

**Current Status:** This project is currently in the research stage.

**Expected Outcomes:** A web application that is specific to highlight the telehealth feasibility and necessity in Alaska. The application should be generalizable to different locations. However, it should focus on Alaska, and as such, the map of Alaska (rather than the whole world) should load when a map-based interface is used.

**Required Skills:** Python or a similar high-level language, and experience in necessary front-end frameworks.

**Code Challenge:** Prior experience working with similar frameworks and projects in the language of choice.

**Source Code:**  https://github.com/KathiraveluLab/TENeT (New Project)

**Discussion Forum**: https://github.com/KathiraveluLab/TENeT/discussions/

**Effort:** 350 Hours

**Difficulty Level:** Intermediate

***





**[10] AAA for Beehive: Authentication, Authorization, and Access Control.**

**Mentors:** David Moxley (dpmoxley -at- alaska.edu) and Pradeeban Kathiravelu (pkathiravelu -at- alaska.edu)

**Overview:** The goal of this project is to test and improve on the data privacy and security aspects of Beehive. Currently, we are hosting Beehive locally and it is used in a controlled environment within the organizational firewalls. However, if we open up Beehive with a public URL, data privacy aspects will play a critical role. Current Beehive implementation did not consider these data privacy and security matters sufficiently. Furthermore, the Clark APIs are likely not fully utilized, as currently they are used in authentication - but many features and functionalities are run without checking for authorization. This project aims to address these critical security and data privacy shortcomings in Beehive.

**Current Status:** The Beehive project is functionally complete. However, it has severe limitations in authentication, authorization, and access control. While several measures are taken for authorization and authentication, the approaches were largely untested for various cases. Also, some of the design choices might be questionable. Rather than having an external API key provider, such as Google Cloud and Clerk, we might have used an API gateway such as Kong, Tyk, or API Umbrella, and used their authentication, authorization, and access control mechanisms. There are some security flaws, in terms of authorization and access control, as can be observed from the issue tracker.

**Expected Outcomes:** The system should be secure. But the signup process should be fairly easy. Email-based signups are ok. Log-ins should be straightforward. A simple username and password should be sufficient. The system should avoid unnecessary bloat and complex installation steps, to enable easy installation in healthcare networks. Consider using a locally deployed API Gateway and its API key-based features to protect access to Beehive front-end. This could complement or replace the current Clerk and Google cloud-based authentication.

**Required Skills:** Python, Computer and Network Security, and API Gateways.

**Code Challenge:** Prior experience working with Python and knowledge in security testing are essential. Experience with API Gateways is a plus. Pull requests are welcome.

**Source Code:** https://github.com/KathiraveluLab/Beehive

**Discussion Forum:** https://github.com/KathiraveluLab/Beehive/discussions

**Effort:** 350 Hours

**Difficulty Level:** Hard

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
