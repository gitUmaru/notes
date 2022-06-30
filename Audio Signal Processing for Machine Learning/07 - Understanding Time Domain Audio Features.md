# Understanding Time Domain Audio Features

## Time Domain Features
- Amplitude envelope (AE)
- RMS Energy 
- Zero crossing rate (ZCR)

### Amplitude Envelope
- Max amplitude value of all samples in a frame
$$AE_t = \max_{k=t\cdot K}^{(t+1)\cdot K-1} s(k)$$
- Between firs tsample of frame $t$ and the last sample of frame $t$
- The above equation computes the $AE_t$ for all frames
- Recall [[06 - How to Extract Audio Features]]  
![[Pasted image 20220520155348.png]]

- Gives rough idea of loudness
- Sensitive to outliers
- Onset detection, music genere classification

### RMS Energy
- RMS ofd all samples in a frame

$$RMS_t = \sqrt{\frac{1}{K}\sum_{k=t\cdot K}^{(t+1)\cdot K-1} s(k)^2}$$
- Indicator of loundess
- Less sensitive to outliers than $AE_t$
- Audio segmentaiton, music genere classification


### ZCR
- Number of times a signal corsses the horizal axis

$$ZCR_t = \frac{1}{2} \cdot \sum_{k=t\cdot K}^{(t+1)\cdot K-1}  | sgn(s(k))-sgn(s(k+1))|$$
- Recognition of percussive vs pitched sounds
- Monophonic pitch estimation
- Voiced/unvoiced decision for speech signals
	- Usually have lower ZCR in voice than unvoiced