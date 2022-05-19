# Types of Audio Features

## Why Audio Features
* Descriptions of couns
* Different features capture different aspects of sound
	* Build intelligent audio systems
	* Pass these features into ML model to effectively learn


## Audio feature categorisation
* Level of abstraction
* Temporal Scope
* Music aspect
* Signal domain
* ML approach


### Level of abstraction
We can break down into three differeant level of the features:
* High level
	* Map to musical constructs that we humans understand
	* ie. instrumentation, key chords, melody, rhythm, temo, lyrics, genre, mood
* Mid level
	* ie. pitch- and bea-related descriptors, such as not onets, flucations patterns, MFCCs
* Low level
	* Features that make sense for the machine but not humans
	* Statistical features almost
	* ie. amplitude env., spectral centroids, spectral flux, zero crossing rate

### Temporal scope
* Instantaneous ($\approx$ 50ms)
	* Notes, etc
	* The exact thing at that moment
* Segment level (on the scale of seconds)
	* Features that give us information about a bar or musical phrase
	* Provides us information that makes sense in a musical context.
* Global
	* Almost like aggregate features
	* On the whole scale
	* One descriptor for the whole thing

### Music aspect
* Beat, Timbre, Pitch, Harmony
	* [[03 - Intensity, Loudness, and Timbre]]
* What about audio in general?

### Signal Domain
* Time domain
	* amplitude envelope RMS energy, zero crossing rate
![[Pasted image 20220516154207.png]]
	* Captured in a wave form
		* Problem: Sound is characterized by frequency, which is not really captured within the time domain.
		* The solution
* Frequency Domain
	* band energy ratio, spectral centroid, spectral flux
	* We apply the fourier tranform to translate from the **time domain** to **freq domain**
![[Pasted image 20220516154429.png]]
	* We have information about all the frequencies that make up the sound
	* Wouldn't it be nice if we had both time and freq, well we do!
* Time-Frequency Representation
	* Spectrogram, Mel-spectrogram, Constant Q transform
![[Pasted image 20220516154728.png]]

## Machine Learning Approach
* Make distinction between traditional ML and more DL type technques

### Traditional ML
* Use all the possible features
* Amplitude envelope, RMS energy, spectral flux, etc

### Deep Learning
* For example, in image processing we pass the image, not the pre-processed version of it in some way
* But we can pass  different domains into it (represenations of the sound)

## Types of intelligent audio systems
* Digital Signal Processing -> rule-based system
* Traditional ML -> feature engieering
* Deep learing -> automatic feature extraction