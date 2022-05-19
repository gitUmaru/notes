# Extracting Audio Features

## Time-domain Feature Pipeline
1. The first step is to look at an analog sound and convert it into something that we can manipulate digitally
	* So we just use an ADC to do this
		* We must sample and define bit rate
		* [[02 - Sound and Waveforms]]
2. After we do this, we must do **framing**
	* Defines segments or frames from which samples begin and end
	* They overlap? Why?
		* Hmm
	* But why must we frame?
	* 
## Frames
- Perceivable audio chunks
- 1 sample @ 44.1 kHZ = 0.0227 ms
- Duration 1 sample << Ear's time resolution (10ms)
	- Cannot appreciate sound samples below 10ms as acoustic events
- Power of 2 num. samples
	- Frame size
	- Usually a power of 2
	- Why?
		- When we apply a FFT, having a 2-based number sample expedites the process (makes it faster algorithmically and asymptotically)
	- Typical values: 256 - 8192
	- Eqn:
$$d_f = \frac{1}{s_r}\cdot K$$
		- $d_f$ is duration
		- $s_r$ is sample rate
		- $K$ is frame size
* Normal frame size is roughly 512, so typical duration is 11ms


## Back to pipeline
3. Feature computation
4. aggreations
	- mean, median, GMM
5. feature value/vector/matrix

## Freq-domain feature pipeline
1. Apply ADC
2. Frame
	-  What's next?
- Want to Go from time to freq domain
	- Use a FFT
	- Think of it like a black box for now
	- But we must consider **spectral leakage**
		- Processed signal isn't an integer number of periods
		- Endpoints are discontinous
		![[Pasted image 20220516160613.png]]
		- If we have this, then these discontinitoies get translated in the spectrum or freq domain as high freq components taht don't actually exist
		- Discontinuities appear as high freq compnents not present in the original signal
		- We can fix this via windowing
### Windowing
- Applying windowing function to each frame
- Eliminates samples at both ends of a frame
- Generates a periodic signal
$$w(k) = 0.5 \cdot \left(1-\cos\left(\frac{2\pi k}{K-1}\right)\right), \forall k \in [0, K]$$![[Pasted image 20220516161521.png]]
- We can do this by:
$$s_w(k) = s(k)\cdot w(k),  \forall k \in [0, K]$$
Where $s(k)$ is the original signal

- But now we have another big problem
	- We lose signal since we applied a windowing frames
	- SOLUTION
		- We use overlapping frame!
		- It all comes together
	- This accounts for the information that we lose at the end point

## Back to pipeline
3. Windowing
4. FFT
5. Feature computation
6. Aggregation
7. Feature, value, vector, matrix
