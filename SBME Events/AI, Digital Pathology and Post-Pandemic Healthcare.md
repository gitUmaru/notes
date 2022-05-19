# AI, Digital Pathology and Post-Pandemic Healthcare
**Hamid R. Tizhoosh**
*Department of Artifician Intelligence and Informatics, Mayo Clinics*

## Microscopy and History
- Currently going through a transformation in Pathology
- History of microscope
- Microscope is the "symbol" of science
	- Trying to replace the symbol with a monitor

## Modern Pathology
- The general pathology workflow
	1. Hospital
	2. Patient
	3. Processing
	4. Distribution
	5. Inspection
	6. Reporting and Retrieval
- But also:
	- Telepathology, diagnositc consultation, collaborative research
- Glass slides are very important

### Virtual Microscopy
- Now we want to digitize pathology slides
- But the microscope is still there
	- Still has the optics
	- Someone has to setup the apparatus to even begin whole slide imaging
	- Pathologist have lost control of image acquisition

## Whole Slide Images
- Because the images are soo big, you need an image viewer
- A general frustration for patholgists
- Magnification $\neq$ resolution
- Optical resolution = f(objective lenses)
- Digital resolution = f(objective lens, digital camera sensor, monitor)
- ![[Pasted image 20220519111429.png]]
- But the benefits of going digital!
	- Example:
		- Efficient workflows
		- conntexted teams
		- increased safety
		- telelpathology
		- **new insights from analyzing large datasets**
			- something that you can't get from traditional microscopy
		- *remote sign-out during crises*
		- Pathologists want to go digital but they're not the decision makers
	- Scanners cost are NOT the barrier
	- STORAGE is the cost barrier


## Major Concerns
Three questions left
- Major Concerns
	- Blurring
	- Missing (fade) tissues
	- Diagnostic equivalence
		- Most impactful concern
		- "Is it really the same if I diagnose with digital images as I would with microscopes"?
		- Of course!
- College of Pathologists Reccomendations
	- The validation shuold encompass the entuire WSI system
		- Scanner
		- Computer
		- Monitor
	- Validation process should include a sample set of atleast 60 cases for one applications
	- Establish dianostic concordance


![[Pasted image 20220519112059.png]]
![[Pasted image 20220519112132.png]]
*Source: Whitepaper, "How to go digital in pathoilogy", LabPON laboratorium Pathologie*

## AI and Digital Pathology
- This also opens ups avenues for computer vison
- When we say "AI", we really mean deep networks
	- Not Fuzzy Systems (FS), MHO

### Can AI Learn Histology
- If I give an image, can it tell what it is?
	- Image -> Epithelium
- We have to spend some time fundeneatlly teaching AI histolgy

#### Fundemental AI Tools for Image Understaning
- Convolution
	- Convolutional Neural Networks
- Generation
	- Adversarial Concepts
- Attention
	- Vision Transformers


* Tissue Representatin
	* Image -> Deep Network -> Feature space
* Patient Representation
	* Use model consisting of
		* Image data
		* Genome/Exome
		* Textual Data
	* Very difficult
	* We come out with a patient representation
* No pathologist makes a decision based on images alone


#### WSI and Molecular Data
![[Pasted image 20220519112954.png]]
- Take a look at an image and predict diagnosius and RNASeq 
- Tissue iamges indexed with RNA-seq info
- Implicit multi-modal tissue searching

#### WSI and Natural Language
- Many ways to say same diagnosis with the complexity of language
- Using highly sophisticated anatomical language
- Leverage Pathology reports
	- Use structured (synoptic)
- Use simple techniques
	- frequency of words, patterns, etc
![[Pasted image 20220519113311.png]]

- Interested in **embeddings** and not the actual predictions per say
- Image encodings through attentionm

## Search and Matching
- AI operating on indexed multi-modela data
- Send image query and get POST response of similar cases images with text embeddings
	- Getting metadata: molecular data, reports, ...
	- Get back to visualization to Pathologist
- **Why Search?**
	- Getting a computational second opinion

### Challenges in Processing WSI
- No labelled data generated
- The incredible high resolution of images
- Pattern diveristy and pleomorphism

## The Source of (almost) all Problems
- Variability in observations
	- Inter- and Intra- observer variability
- **Intraobservbility** is especially dificult
	- Why? Hesienberg uncertainty principle
	- The closer you look at reality, the harder it is to know what it is
- Can AI remove observer variability
	- Classification is not the solution
		- Trusing the computer to ascertain ground truth
	- Give it to a search engine?
		- One physician has to accept what many other physicians say

## AI, Overfitting, Bias, and Shortcuts
- Deep networks are failgin the turing test
- NNs are able to determine the insitiution from which images came from
	- 91% AUC that these images are from JHU or Mayo or whatever
- **External validation** is a foreign wor in AI community
	- Train, Validate, Test, Xvalidate
	- Many domains, different instances
	- Bring images from other hospitals


## What is Coming?
- Changes in PHM strats
- High demand for telemedicine and RPM
- Increase in adoption of digital pathologyu
- INcrease in cloud deployment and HPS
- Significant intensification of discovery resreaech
	- Exploiting biobanks and AI

## Questions
- Thank you Dr. Tizhoosh, that was a wonderful talk! This might be a silly question but if there are recognizable features in WSI between domains, can we use those features as apart of image augmentation to train deep networks more diversely?
