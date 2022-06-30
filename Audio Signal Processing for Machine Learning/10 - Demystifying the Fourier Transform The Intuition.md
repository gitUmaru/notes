# Demystifying the Fourier Transform: The Intuition

## Intuition
- Decompose a complex sound into its frequency components
- What we do really is a **journey** from time to frequency domain
![[Pasted image 20220520163602.png]]


## Deeper Intuition
- Compare signal with sinusoids of various frequencies
- For each ferq we get a magnitude and a phase
	- High magnitude indicates a high similarity between the signal and a sinusoid
	- Absolute value of a FFT iis the *magnitude*
- Recall [[01 - Sound and Waveforms]] for recollection of vocob
- Sine wave

$$\sin (2\pi \cdot (ft-\phi))$$
- Fourier Transform: Step by step
	1. Choose a frequency
	2. Optmise phase
	3. Calculate magnitude
	4. Repeat!


Hence:

$$\phi_f = \arg \max_{\phi\in[0,1)} \left(\int s(t) \cdot \sin\left(2\pi \cdot (ft-\phi)\right)\right); \forall f,t \in \mathbb{R} $$
$$d_f = \max_{\phi\in[0,1)} \left(\int s(t) \cdot \sin\left(2\pi \cdot (ft-\phi)\right)\right); \forall f,t \in \mathbb{R}$$

## Reconstructing a Signal
- Superimpose sinusoids
- Weight them by the relative magnitude
- Use a relative phase
- Original signal and FT signal contain the same information