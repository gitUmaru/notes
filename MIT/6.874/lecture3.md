# Convolutional Neural Networks

## Scene Understanding

Human Vision $\iff$ many layer of abstraction $\iff$ Deep learning

Foundations go back back to early neuroscience ideas. Based on the discoveries of:

1. Receptive fields = local computation
2. Simple cells = edge/orientation detectors
	* Basically certain neuron would fire once an image was rotated and not fire when in different orientation
3. Complex cell = position invariance/pooling
	* These cells fire regardless of the image orientation
	* At the basis of the pooling operation in CNNs
		* Was there even something there?
		* Based on edge detections findings
* Layers: pixels, edges (bands given slant, contrast edges), shapes, primitives, scenes
* Hierarchical abstractions, simple building blocks, local computation, learning, invariance

### Primitives

![](https://i.imgur.com/yvVJ7u9.png)

* Chemical accumulation across dendritic connections
* Pre-synaptic axon
	* post-synaptic dendrite
	* neuronal cell body

* Each neuron receives multiple signals from its many dendrites
* When **threshold** crossed, it fires 
	* What we're talking about with activations functions
* Its axon then sends outgoing signal to downstream neurons

* Weak stimuli ignored 
* **Activation function** signal threshold crossed 
* **Non-linearity** within each neuronal level

![](https://i.imgur.com/xIMprQ0.png)

* **Neurons** connected into **circuits** (neural networks): **emergent** properties, **learning**, memory 
* Simple primitives arranged in simple, repetitive, and extremely **large** and **deep** networks 

Mapping single neuron to very simple ideas (position, orientation, colour, etc) that fire depending on stimuli

### Abstraction layers
Like edges, bars, dir., shapes, objects, scenes

* Coupling these neurons can begin to form more complex functionality
* Neurons fire in **frequency** and **not** amplitude
* Primitives of visual concepts encoded in neuronal connection in early cortical layers
* **Deep**: Abstraction **layers** $\iff$ visual cortex layers 
* **Complex concepts** from simple parts, **hierarchy**

![](https://i.imgur.com/NtrsSBK.png)

* Interchangeable circuitry
* Auditory cortex learns to ‘see’ if sent visual signals
* Injury area tasks shift to uninjured areas

Visual illusions basically allow the same primitives to fire between two similar images

![](https://i.imgur.com/OBt6iQh.png)![](https://i.imgur.com/xDEiQXA.png)

* Visual illusions reveal brain **primitives**, building blocks, computations, architecture
	* High level frequency clash with low level frequencies
* Deep learning can exploit such conflicting **primitives** to create strong experiences, or for **adversarial** ‘confusions’ of ML systems

## CNN Foundations

### Key Ingredients of CNN

![](https://i.imgur.com/ttQTMq9.png)


#### Key Idea: Representation Learning

![](https://i.imgur.com/L3HgPbV.png)

In deep learning, the two tasks are **coupled**:
* the classification task “drives” the feature extraction
* Extremely powerful and general paradigm 
	* Be creative! The field is still at its infancy!
	* New application domains (e.g. beyond images) can have structure that current architectures do not capture/exploit
* Genomics/biology/neuroscience can help drive development of new architectures

#### Key Idea: Reuse Parameters
* Convolution shares parameters
* Example 3x3 convolution on a 5x5 image
 
1) Apply a set of weights – a filter – to extract local features
2) Use multiple filters to extract different features
3) Spatially share parameters of each filter

**Feature Extraction with Convolution**.

- Filter of size 4x4 : 16 different weights
- Apply this same filter to 4x4 patches in input
- Shift by 2 pixels for next patch

#### Key Idea: Filters extract Features

![](https://i.imgur.com/F1rZZeH.png)


Previously, we hard coded these kernels/ filters; however now we're learning these kernels *de novo*

![](https://i.imgur.com/JbkdivK.png)

If certain kernels are not useful, then they will not "evolve"

#### Key Idea: Learn Hierarchy of features directly from the data
Rather than hand-engineering them

![](https://i.imgur.com/67qnj5f.png)

Learning the features *de novo* as we give the network the data and such.

### Pooling Layers: Positional Invariance

![](https://i.imgur.com/r4l8T6S.png)

Pooling reduces dimensionality by giving up spatial location

* max pooling reports the maximum output within a defined neighborhood
* Padding can be SAME or VALID

### Classification: Fully-connected layers
Fully Connected:
* Each neuron in hidden layer connected to all neurons in input layer
* No spatial information
* Many, many parameters

### Edge Cases (Literally)

![](https://i.imgur.com/Li3d5Zp.png)

![](https://i.imgur.com/uZS23w8.png)


### Feature Invariance: Data Augmentation
Feature invariance to perturbation is hard

![](https://i.imgur.com/OSi8xpr.png)

![](https://i.imgur.com/t4uUxal.png)


## Modern CNN Architecture
### LeNet-5
Gradient Based Learning Applied To Document Recognition - Y. Lecun, L. Bottou, Y. Bengio, P. Haffner; 1998

• Helped establish how we use CNNs today
• Replaced manual feature extraction

![](https://i.imgur.com/3B3cB5K.png)


Only 60K parameters
* As we go deeper in the network: 
	* 𝑁𝐻, ↓, 𝑁𝑊, ↓, 𝑁𝐶, ↑
* General structure:
	* conv->pool->conv->pool->FC->FC->output

* Different filters look at different channels
* Sigmoid and Tanh nonlinearity


## Countless Applications

Ran out of time

:P