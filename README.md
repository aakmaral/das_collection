# Awesome DAS Collection [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated collection of Distributed Acoustic Sensing (DAS) research, datasets, code, tools, and resources (from 2020 onwards).

Distributed Acoustic Sensing (DAS) turns fiber optic cables into thousands of sensors, enabling high-resolution monitoring for seismology, infrastructure, environmental studies, and more. This list organizes key papers, datasets, software, and community resources in the rapidly evolving DAS field.

## Contents

- [Research Papers](#research-papers)
  - [Fundamentals](#fundamentals)
  - [Seismology](#seismology)
  - [Infrastructure Monitoring](#infrastructure-monitoring)
- [Datasets](#datasets)
- [Code & Tools](#code--tools)
  - [Signal Processing](#signal-processing)
  - [Visualization Tools](#visualization-tools)
  - [Analysis Pipelines](#analysis-pipelines)
- [Python Libraries](#python-libraries)
- [Related Projects](#related-projects)
- [Contributing](#contributing)
- [License](#license)

## Research Papers (2020 -- Present)

### Fundamentals

- [Removing Instrumental Noise in DAS Data: Two Deep Learning Approaches](https://doi.org/10.3390/rs16224150) (2024) – Gu et al. compare a supervised deep learning method (using synthetic clean data with real noise added) and a Noise2Noise (N2N) approach for eliminating interrogator-induced noise in DAS. Both methods successfully remove hardware noise within the signal band, boosting the DAS data SNR beyond what conventional filtering can achieve. *Tags: DAS denoising, instrumental noise, supervised vs. unsupervised.* **Code:** [CEGCurtin/DASDenoisingML_MultipleInterrogators](https://github.com/CEGCurtin/DASDenoisingML_MultipleInterrogators) (Curtin Univ.).

- [Self-Supervised Coherence-Based Denoising of Cryoseismological DAS Data](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2024JH000414) (2025) – Zitt et al. present a self-supervised deep learning approach that leverages signal coherence to denoise DAS recordings in glacial environments. The method improves the detection of microseismic icequakes, with 66 of 120 DAS sections showing identifiable events before denoising and significantly enhanced signal clarity after applying the coherence-based Noise2Noise training. *Tags: DAS denoising, self-supervised, cryoseismology.* **Code:** [JohannaZitt/CryoDASDenoising](https://github.com/JohannaZitt/CryoDASDenoising).

- [Unlocking DAS Amplitude Information via Coherency Coupling](https://doi.org/10.26443/seismica.v4i1.1488) (2025) – Hudson et al. present a method using coherency to pragmatically estimate coupling of fibre to the medium. They first introduce a theoreticaljustification relating coherency to relative coupling between channels and calibrating this to obtain absolutecoupling coefficients, before evidencing the performance of the method using various examples from glaciersto downhole geothermal deployments. They apply the method to estimate earthquake magnitudes, comparingvalues to independent geophone estimates. *Tags: DAS amplitude, coupling.* **Code:** []().

- [Automatic Identification of High-Quality Channels in Distributed Acoustic Sensing Through Implementation of a Channel Quality Index](https://ieeexplore.ieee.org/document/11098723) (2025) - Rodriguez et al. developed a channel quality index (CQI), a machine-learning-based approach that automatically identifies high-quality DAS channels based on their ability to record earthquake signals. Trained on data from four offshore DAS experiments in the Spanish Mediterranean and Canary Islands, the model evaluates temporal, frequency, and energy-based features to assign quality scores to individual channels. *Tags: DAS amplitude, channel quality, coherency.* **Code:** [B-CSI/cqi_das](https://github.com/B-CSI/cqi_das).

- [Denoising Offshore Distributed Acoustic Sensing Using Masked Auto-Encoders to Enhance Earthquake Detection](https://agupubs.onlinelibrary.wiley.com/doi/abs/10.1029/2024JB029728) (2025) - Shi et al. develop a self-supervised deep learning algorithm, a masked auto-encoder (MAE), to denoise DAS data for seismological purposes. The model is trained on DAS recordings of local earthquakes with randomly masked channels acquired on fiber-optic cables in the Cook Inlet offshore Alaska. To demonstrate the benefits of denoising for seismological research, they conduct the most fundamental steps to build any earthquake catalog: seismic phase picking, signal-to-noise ratio (SNR) estimation, and event association.  *Tags: DAS denoising, instrumental noise, self-supervised.* **Code:** [Denolle-Lab/Shi_etal_2023_denoiseDAS](https://github.com/Denolle-Lab/Shi_etal_2023_denoiseDAS).

- [Noise Attenuation via Guided Unsupervised Deep Learning](https://doi.org/10.1190/geo2024-0109.1) (2024) – Saad, Ravasi et al. develop a new approach to denoise DAS data that leverages an unsupervised deep learning (DL) model, eliminating the need for labeled training data. The input DAS data undergo band-pass filtering to eliminate high-frequency content. Subsequently, a continuous wavelet transform (CWT) is performed, and the finest scale is used to guide the DL model in reconstructing the DAS signal.  *Tags: DAS denoising, unsupervised learning, U-Net.* **Code:** [DeepWave-KAUST/DLDAS_Denoising-pub](https://github.com/DeepWave-KAUST/DLDAS_Denoising-pub).

- [DAS-N2N: Weakly Supervised Denoising without Clean Data](https://www.semanticscholar.org/paper/0ac944059230fd503e097fd6b6f0b96bdae57a66) (2024) – Lapins et al. introduce a Noise2Noise-style deep learning method, DAS-N2N, that suppresses incoherent noise using only paired noisy DAS signals for training. The model significantly boosts the SNR of weak signals (e.g. microseismic icequake events) and is inherently robust to varying noise conditions. Notably, DAS-N2N achieved comparable performance to supervised methods while requiring no ground-truth clean data. *Tags: DAS denoising, weakly supervised, Noise2Noise.* **Code:** [sachalapins/DAS-N2N](https://github.com/sachalapins/DAS-N2N).

- [Wavefield Reconstruction & Compression for DAS](https://agupubs.onlinelibrary.wiley.com/doi/10.1029/2024JH000247) (2024) – Ni et al. develop machine-learning techniques for efficient wavefield reconstruction of DAS data, addressing challenges of data volume and mixed wavefields. They test various architectures to treat DAS data as two-dimensional arrays, such as the Implicit Neural Representation (INR) models and the SHallow REcurrent Decoder (SHRED) model.  *Tags: DAS compression, wavefield separation, edge computing.* **Code:** [niyiyu/DAS-reconstruction](https://github.com/niyiyu/DAS-reconstruction).

### Seismology

- [Fin Whale Vocalization Enhancement via DAS](https://pubs.aip.org/asa/jasa/article/157/5/3655/3346872/Enhancing-fin-whale-vocalizations-in-distributed) (2025) – Goëstchel, Wilcock, Abadi et al. demonstrate using a subsea telecom fiber as a DAS hydrophone array to detect 20 Hz fin whale calls. They apply signal processing to boost whale vocalizations in noisy DAS strain-rate data and convert strain measurements to equivalent acoustic pressure. Despite current noise limitations, their JASA study shows DAS can complement hydrophones for marine mammal monitoring. *Tags: DAS ocean acoustics, marine bioacoustics, fin whales.* **Code:** [Ocean-Data-Lab/Goestchel_JASA_2025](https://github.com/Ocean-Data-Lab/Goestchel_JASA_2025).

- [RNN-DAS for Volcano Seismicity](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2025JB031756) (2024) – Fernández-Carabantes et al. develop an LSTM-based recurrent neural network for real-time detection and monitoring of volcano-tectonic events using DAS. RNN-DAS achieves high accuracy in recognizing volcanic micro-seismic signals from fiber-optic data, enabling prompt identification of earthquakes and tremor during volcanic unrest. *Tags: DAS seismology, volcano monitoring, RNN.* **Code:** [Javier-FernandezCarabantes/RNN-DAS](https://github.com/Javier-FernandezCarabantes/RNN-DAS).

- [Earthquake focal mechanisms with distributed acoustic sensing. Nature Communications](https://www.nature.com/articles/s41467-023-39639-3) (2023) - Authors present a data-driven method that measures P-wave polarities on a DAS array based on cross-correlations between earthquake pairs. *Tags: DAS, earthquake detection, polarities.* **Code:** [jxli2a/dasfm_demo](https://github.com/jxli2a/dasfm_demo).

- [Better Together: Ensemble Learning for Earthquake Detection and Phase Picking](https://ieeexplore.ieee.org/document/10266366) (2023) - Authors propose a new processing workflow that integrates pretrained DL models, multifrequency band predictions, and ensemble estimations to enhance the generalization of these algorithms. They compare an ensemble approach with a transfer-learning approach and discuss the benefits and drawbacks of these two approaches when deploying on continuous data. *Tags: DAS seismology, earthquake detection, phase pcking.* **Code:** [congcy/ELEP](https://github.com/congcy/ELEP).

- [Landslide Monitoring with DAS](https://www.nature.com/articles/s41467-024-50604-6) (2023) – Oullet et al. reveal previously hidden landslide processes using low-frequency DAS measurements at the Hollin Hill landslide site. They identified subtle precursory strain signals and internal slide dynamics that conventional sensors missed, demonstrating DAS's ability to capture slow ground deformations in geohazard monitoring. *Tags: DAS geophysics, landslides, low-frequency signals.* **Code:** [smouellet/hhdas](https://github.com/smouellet/hhdas).

- [Deep Deconvolution for Traffic Analysis With Distributed Acoustic Sensing Data](https://ieeexplore.ieee.org/document/9966323)(2022) - Authors propose a self-supervised Deep Learning approach that deconvolves the characteristic car impulse response from the DAS data, which they refer to as a Deconvolution Auto-Encoder (DAE). They show that deconvolution of the DAS data with our DAE leads to better temporal resolution and detection performance than the original (non-deconvolved) data. *Tags: DAS traffic, deconvolution, self-supervised.* **Code:** [Juanx65/DeepDeconv](https://github.com/Juanx65/DeepDeconv). **Code:** [Juanx65/DeepDeconvV2](https://github.com/Juanx65/DeepDeconvV2).

### Infrastructure Monitoring

- [Characterizing Vehicle DAS Signals for Imaging](https://pubs.geoscienceworld.org/ssa/srl/article-abstract/96/5/2867/653701/Characterizing-Vehicle-Induced-Distributed?redirectedFrom=fulltext) (2025) – Liu et al. analyze how different vehicles induce different DAS wavefields to improve urban near-surface imaging. By classifying vehicle-induced DAS signals (cars vs. heavy trucks) and studying their dispersion, they can extract more accurate surface-wave information for imaging the shallow subsurface. This work enables "traffic-based" seismic surveys in cities, turning passing vehicles into signal sources for urban geophysics. *Tags: DAS ambient vibrations, vehicle characterization, urban geophysics.* **Code:** [jingxiaoliu/das_diff_veh](https://github.com/jingxiaoliu/das_diff_veh).

- [Smart Fiber-Optic Distributed Acoustic Sensing (sDAS) With Multitask Learning for Time-Efficient Ground Listening Applications](https://ui.adsabs.harvard.edu/abs/2024IITJ...11.8511W/abstract) (2024) – Wu et al. propose sDAS, a smart fiber-optic sensing system using multi-task deep learning for time-efficient ground surveillance. Their IEEE IoT study integrates tasks like event detection and classification (e.g. identifying vehicles vs. digging) into one model, enabling real-time "ground listening" along critical infrastructure. *Tags: DAS IoT, multi-task learning, smart city.* **Code:** [kdxy2233/MTL-DAS.PyTorch](https://github.com/kdxy2233/MTL-DAS.PyTorch).

- [DAS Event Classification via Vision Transformers](2024) – They apply Vision Transformer models to DAS event classification. By converting DAS time-series data (strain vs. time) into spectrogram images, they leverage ViT architectures to classify events (e.g. footsteps, vehicles) with high accuracy. This approach takes advantage of transformers' ability to capture global patterns in the "images" of DAS signals, improving upon traditional CNN-based classifiers for complex DAS datasets. *Tags: DAS event classification, vision transformer, deep learning.* **Code:** [tkks22123/DAS-Event-Classification-using-Vision-Transformers](https://github.com/tkks22123/DAS-Event-Classification-using-Vision-Transformers).

- [Movement Detection in DAS](2024) – Balewski provides algorithms for detecting movement events in continuous DAS recordings. This toolset focuses on identifying vibrations caused by human or vehicle movement in noisy fiber optic data, which is crucial for security monitoring (e.g. detecting intruders near pipelines or perimeters). The methods include signal conditioning and pattern recognition to discern movement-induced strain signals from background noise. *Tags: DAS security, motion detection, signal processing.* **Code:** [PBalewski/Movement-detection-in-DAS-recordings](https://github.com/PBalewski/Movement-detection-in-DAS-recordings).

## Datasets


- [DASAttn DATASET](https://ieee-dataport.org/documents/dasattn-dataset)

- [Utah FORGE: High-Resolution DAS Microseismic Data from Well 78-32](https://gdr.openei.org/submissions/1185) 

- [PubDAS a PUBlic Distributed Acoustic Sensing datasets repository for geosciences](https://eartharxiv.org/repository/view/3574/) 

- [Comprehensive Dataset for Event Classification Using Distributed Acoustic Sensing (DAS) Systems](https://springernature.figshare.com/articles/dataset/Comprehensive_Dataset_for_Event_Classification_Using_Distributed_Acoustic_Sensing_DAS_Systems/27004732?file=52736258) 

- [RAPID: Distributed Acoustic Sensing on the OOI’s Regional Cabled Array](https://oceanobservatories.org/pi-instrument/rapid-a-community-test-of-distributed-acoustic-sensing-on-the-ocean-observatories-initiative-regional-cabled-array/)

- [RAPID: Multiplexed Distributed Acoustic Sensing (DAS) at the Ocean Observatory Initiative (OOI) Regional Cabled Array (RCA)](https://oceanobservatories.org/pi-instrument/rapid-multiplexed-distributed-acoustic-sensing-das-at-the-ocean-observatory-initiative-ooi-regional-cabled-array-rca/)

- [HDAS Data from La Palma - DigiVolCan Project](https://zenodo.org/records/15105596)

- [Replication Data for: Array Analysis of Seismo-Volcanic Activity with Distributed Acoustic Sensing](https://dataverse.ipgp.fr/dataset.xhtml?persistentId=doi:10.18715/IPGP.2023.lgl6bxby)

- [Brady's Geothermal Field DAS Vibroseis Data](https://gdr.openei.org/submissions/849)

- [Distributed Acoustic Sensing Experiment Data from Garner Valley, California](https://gdr.openei.org/submissions/614)

- [Belgium Distributed Acoustic Sensing Array Raw Data](https://data.caltech.edu/records/2vdrb-bmr68)

- [Photonic seismology in Monterey Bay : Dark fiber DAS illuminates offshore faults and coastal ocean](https://github.com/njlindsey/Photonic-seismology-in-Monterey-Bay-Dark-fiber1DAS-illuminates-offshore-faults-and-coastal-ocean)

- [Distributed Acoustic Sensing fin whale labeled dataset for level estimations](https://zenodo.org/records/15008561) 

- [SAFOD DAS Earthquake records - full catalog](https://github.com/ariellellouch/DASDetection)

- [Fiber-optic network observations of earthquake wavefields](https://github.com/eileenrmartin/FiberOpticEarthquakes)


## Code & Tools

### Signal Processing

- [DASVaderDS.jl](https://github.com/marianoarnaiz/DASVaderDS.jl) – A Julia toolkit for DAS data processing, offering fast I/O, signal conditioning, and basic analysis pipelines. It can handle large DAS datasets and includes functionality for filtering, decimation, and spectral analysis.

- [FiberSenseAI-DAS](https://github.com/vishnudev-p/FiberSenseAI-DAS) – A web-based anomaly detection system built with Flask that analyzes Distributed Acoustic Sensing (DAS) time-series data. It identifies "shaker" vs "noise" events using a trained KNN classifier and visualizes the anomalies with charts and downloadable reports.

- [ReMi-DAS](https://github.com/Shihao-Yuan/ReMi-DAS) – An implementation of the Refraction Microtremor (ReMi) technique adapted for DAS arrays. 

- [pySEAFOM](https://github.com/SEAFOM-Fiber-Optic-Monitoring-Group/pySEAFOM) – A Python library for performance analysis and testing of Distributed Acoustic Sensing (DAS) interrogators, developed by SEAFOM's Measuring Sensor Performance group. This package provides standardized tools for testing, benchmarking, and performance evaluation of DAS systems following SEAFOM recommended procedures.

- [lightguide](https://github.com/pyrocko/lightguide) (Pyrocko module) – Part of the Pyrocko seismology library, lightguide provides support for DAS data formats and simulations.

- [GenericCable](https://github.com/seisfwi/GenericCable) – A simulation tool that models the strain sensing response of generic fiber-optic cables. 


### Visualization Tools

- [DAS Data Visualization](https://github.com/RachelWillis1/DAS_Data_Visualization) – A Python toolkit for plotting of DAS data. 

- [DAS4Whales](https://github.com/DAS4Whales/DAS4Whales) – A specialized visualization and analysis tool for marine DAS data. 

- [Seismic-DAS Plotting Dashboard](https://github.com/Sruthisl94/Seismic-Data-Analysis-from-Distributed-Acoustic-Sensing-DAS-Data) – Analyze raw seismic DAS data from the Stanford DAS dataset to explore temporal patterns, amplitude variations, and frequency characteristics.


### Analysis Pipelines

- [DAS Event Pipeline (ADAS)](https://github.com/shoaibulhassaan/adas-preprocessing-pipeline/tree/main) – An end-to-end preprocessing pipeline for DAS, which handles raw data conversion, common-mode noise removal, bandpass filtering, and splitting data into analysis windows. It prepares DAS data for input into detection or ML classification algorithms.

- [GreenlanDAS](https://github.com/Denolle-Lab/greenlanDAS) – A pipeline from Denolle Lab for analyzing glacial DAS data (as deployed in Greenland). It automates detection of icequakes, correlation of DAS strain with seismometer data, and produces summary plots of glacial seismicity over time.

- [Pipeline flow characterization using distributed acoustic sensing (DAS)](https://github.com/KieranFitzmaurice/pipelines) – estimating flow velocity and speed of sound in a pipeline using DAS data via an f–k (frequency–wavenumber) Doppler method.


- [Soil Salinity Active-DAS Pipeline](https://github.com/Wave-Lab-UGA/Soil-Salinity-Classification-with-Active-Distributed-Acoustic-Sensing) – Data acquired from a Distributed Acoustic Sensor is used to develop a convolutional neural network for classifying soil by its salinity level. This code contains the data preparation pipeline, model training, and metric evaluation.

- [Unsupervised DAS Anomaly Detection](https://github.com/ahmadtourei/das-anomaly) - An unsupervised anomaly detection in distributed acoustic sensing (DAS) datasets using an autoencoder-based deep learning algorithm.

- [DAS Foundation Model – Event Segmentation](https://github.com/uwfiberlab/FM_Segmentation_DAS) - segmentation subsection for a Distributed Acoustic Sensing (DAS) machine learning foundation model.


## Python Libraries

- [dascore](https://github.com/DASDAE/dascore) – A comprehensive Python library for DAS data.DASCore is part of the DAS Data Analysis Ecosystem (DASDAE).

- [xdas](https://github.com/xdas-dev/xdas) – An open-source framework that defines a standard data structure and API for distributed acoustic sensing data. It supports conversion between vendors' formats and includes modules for basic operations (calibration, moving average gauge length filtering, etc.). xdas facilitates easier sharing of code and data across different DAS hardware.

- [DASPy](https://github.com/HMZ-03/DASPy) – A Python toolbox that includes many utility functions for DAS. Includes classic seismic data processing techniques and specialized algorithms for DAS applications, including denoising, waveform decomposition, channel attribute analysis, and strain-velocity conversion.

- [DASLab](https://github.com/yohanesnuwara/DASLab) – An library that provides tutorial for DAS. It covers reading data, visualizing wavefields, performing cross-correlations for ambient noise, and other fundamental tasks.

- [distpy](https://github.com/Schlumberger/distpy) – A library released for distributed sensing data, it provides massively parallel and scalable DAS interpretation using self-describing branched networks.

- [pyrocko.lightguide](https://github.com/pyrocko/lightguide) – A submodule of Pyrocko (a seismology library) tailored to DAS. It can simulate the propagation of seismic waves in optical fibers (accounting for gauge length and optical propagation effects) and provide synthetic DAS data from known earthquake sources, useful for testing algorithms.

- [DAS_metadata](https://github.com/DAS-RCN/DAS_metadata) – A package defining standardized metadata schemas for DAS experiments (e.g., fiber coordinates, instrument response, coupling medium). It provides JSON/YAML templates and validation tools to ensure consistency in metadata, which is crucial when sharing DAS datasets in repositories or publications.


## Related Projects

- **Awesome Geophysics** – See the [Awesome Geophysics](https://github.com/Pequenopolis/awesome-geophysics?tab=readme-ov-file) list which covers general geophysical paper, tools and datasets.

- **Awesome DAS** - See the [Awesome DAS](https://github.com/DAS-RCN/awesome-das) list of DAS tools and resources.

- **Distributed Fiber Sensing** – Beyond acoustic sensing, distributed fiber sensing includes Distributed Strain Sensing (DSS) and Distributed Temperature Sensing (DTS). Many DAS deployments also collect DSS/DTS. 

- **Hydrophone & Geophone Networks** – DAS is often used with traditional sensor networks. Projects integrating DAS with seafloor hydrophone arrays (for whale monitoring) or with dense nodal seismometer arrays (for urban microzonation) provide valuable insight. 

- **Fiber-Optic Seismic Interferometry** – Related to DAS are efforts using fiber interferometers and point sensors. Projects like Optical Seismic Arrays (using Fiber Bragg Gratings or Fabry-Pérot sensors) sometimes appear in literature. 

- **Standards and Formats Initiatives** – The DAS Research Network and others are working on standardizing data formats (e.g., adapting miniSEED for DAS, or HDF5-based formats). See the [DAS_metadata](https://github.com/DAS-RCN/DAS_metadata) repository in the Code section.

## Contributing

Contributions are welcome! Please read the [contribution guidelines](CONTRIBUTING.md) first.

To contribute:
1. Fork this repository
2. Add your contribution (new resource or improvement)
3. Submit a pull request for review

Please ensure your pull request adheres to the following:
- Search previous suggestions before adding a new resource to avoid duplicates
- Make an individual pull request for each suggestion or category of suggestions
- Use the format: `[Resource Name](link) - Description.` for consistency
- Keep descriptions clear, concise (1-3 sentences), and informative (including purpose or key finding)
- New categories or improvements to the structure are welcome if they enhance organization

By contributing, you help keep this list up-to-date and useful for everyone in the DAS community. Thank you!

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

---

**Maintained by:** [Akmaral Amanturdieva]

**Last Updated:** November 2025

*Have a resource to add? Open an issue or submit a pull request!*
