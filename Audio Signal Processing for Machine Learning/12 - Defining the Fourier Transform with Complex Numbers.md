# Defining the Fourier Transform with Complex Numbers

Recall [[11 - Complex Numbers for Audio Signal Processing]]

## The Intuition
- Use magnitude and phase as polar coordinates
- Encode both coefficients in a single coefficient

### Complex Fourier Transform Coefficients
- We have one of this for each frequency that we decompose
$$c_f = \frac{d_f}{\sqrt2}\cdot e^{-i2\pi \phi_f}$$
$$c = |c|e^{i\gamma}$$

- Recall our representation of complex numbers on the real-imaginary plane
- The negative in the exponent allows us to rotate *clockwise* when the phase increases
	- Important for some reason

#### Continous Audio Signal
$$g(t) \text{ s.t } g: \mathbb{R}\to \mathbb{R}$$
#### Complex Fourier Transform
$$\hat g(f) = c_f \text{ s.t } \hat g : \mathbb{R} \to \mathbb{C}$$

- The output is a point on the complex-real plane
	- Very cool

### Complex Fourier Transform
Now we can mathmatically define the CFT

$$\hat g(f) = \int g(t) \cdot e^{-i2\pi f t} dt$$
![[Pasted image 20220524143511.png]]
 But recall that we can get the REAL part of this by using Euler's Identity.
### Inverse Fourier Transform

$$g(t) = \int c_f \cdot e^{i2\pi ft df}$$