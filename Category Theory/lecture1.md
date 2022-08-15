# Categories


## 1.1: Intro
* category theory is abstraction of the idea of a system of permutations of a set or symmetries of a geometric object
![](https://i.imgur.com/ZtSljne.png)

* A category is just such an “algebra,” consisting of objects $A, B, C$, . . . and arrows $f : A \to B, g : B \to C, \dots$, that are closed under composition and satisfy certain conditions typical of the composition of functions

### Aside
A branch of abstract algebra, category theory was invented in the tradition of Felix Klein’s Erlanger Programm, as a way of studying and characterizing different kinds of mathematical structures in terms of their “**admissible transformations**”. The general notion of a category provides a characterization of the notion of a “**structure-preserving transformation**”, and thereby of a species of structures *admitting such transformations*.

### 1.1 Cont.
* Category theory is the abstract theory of functions
* better have been called *abstract function theory*, or perhaps even better: *archery*
	* I love that

## 1.2: Functions of sets

* We will begin by considering functions between Sets
	* Not defining this, assuming working knowledge
* Let $f$ be a function from a set $A$ to another set $B$
	* $f: A \to B | f \subseteq A \times B$
	* $\mathtt{range}(f) \subseteq B$.
* Suppose $g: B\to C$
* Then there is a composite function such that

$$(g \circ f)(a)  g(f(a)) \hspace{1cm} a\in A$$
Now this operation “$\circ$” of composition of functions is associative, as follows. If we have a further function $h: C \to D$

![](https://i.imgur.com/RbQeZnH.png)

We can note that

$$(h \circ g) \circ f = h\circ (g \circ f)$$
By the way, this is of course is what it means for two functions to be equal: for every argument, they have the same value.

Finally note that, our sets, have an identity functions

$$1_A : A\to A \hspace{1cm} \text{s.t. } 1_A(a) = 1$$

These identity functions act as “units” for the operation ◦ of composition, in the sense of abstract algebra. That is to say,

$$f\circ 1_A = f = 1_B \circ f$$

These are all the properties of set functions that we want to consider for the abstract notion of function — composition and identities. Thus we now want to “abstract away” everything else, so to speak. That’s what is accomplished by the following definition.

## 1.3: Definition fo a category

**Definition 1.1:** A *category* is a collection of items that have arrows between them and have the property of: totality, associativity, composition, and identity.


![](https://i.imgur.com/7AdsxDI.png)

## 1.4: Examples of categories

* Sets
* graphs and graph homomorphisms
* real numbers $\mathbb{R}$ and continous functions $\mathbb{R} \to \mathbb{R}$ 
* topological spaces and continuous mappings
* differentiable manifolds and smooth mappings
* posets and monotone functions


A *poset* is a set $A$ equipped with a binary relation $a \leq_A b$ such that:
$$\forall a,b,c \in A$$Reflexive $$a \leq_A a,$$ Transitivity $$ a\leq_A b \wedge b\leq_A c \implies a \leq_A c,$$ Antisymmetry $$ a\leq_A b \wedge b \leq_A a \implies a =  b $$

What does it take for this to be a category? We need to know that $1_A : A \to A$ is monotone, but that is clear since $a \leq_A a'$  implies $a \leq_A a'$ . We also need to know that if $f: A \to B$ and  $g: B → C$ are monotone

then $g \circ f : A \to C$ is monotone. This also holds, since $a \leq_A a'$ implies f(a) ≤ f(a ′ ) implies g(f(a)) ≤ g(f(a ′ )) implies (g ◦ f)(a) ≤ (g ◦ f)(a ′ ). So we have the category **Pos** of posets and monotone functions.

Try this one on your own:

Prove that **Rel** is a category.
![](https://i.imgur.com/VNIqk8X.png)



We should also look at at the arroows or mappgins between categories.

A "homomorphism of categories" is called a **functor**

**Definition 1.2:** A function $F: \textbf{C} \to \textbf{D}$ between categories $\textbf{C}$ and $\textbf{D}$ is a mapping of objects to objects and arrows to arrows, in such a way that:

a. $F (f: A\to B) = F(f) : F(A) \to F(B)$
b. $F(g\circ g) = F(g) \circ F(f)$
and c. $F(1_A) = 1_{F(A)}$

Functors have identity functors

Hence, another category : $\mathbf{Cat}$, the category of all categories and functors


Another important category: **Monoid**

A set $M$ equipped with a binary operation $\cdot : M \times M \to M$ and a distinguished "unit" element $u \in M$ sucht that $\forall x,y,z \in M$

$$x\cdot(y\cdot z) = (x\cdot y)\cdot z$$
and
$$u\cdot x = x = x \cdot u$$

Equivalently, a monoid is a category with just one object. The arrows of the category are the elements of the monoid.

Honestly, understanding monoids will take some time to digest; unfortunately, you just need to keep rereading the definition of monoids untill it clicks. :P

[A cool video I found that helped me ](https://www.youtube.com/watch?v=fRJMggrpxRU)

## 1.5: Isomorphisms
**Definition 1.3.** I any category $\mathbf{C}$ an arrow $f: A \to B$ is called an *isomorphism* if there is an arrow $g: B \to C$ in $\mathbf{C}$ such that
$$g\circ f = 1_a \wedge f\circ g = 1_B$$

Since inverses are unique, we can say that $A$ is isomorphic to B  ($A\cong B$) if there exists an isomorphism between them

> Two objects in a category are isomorphic if there is a way to go to the other object and come back

**Definition 1.4.** A *group* $G$ is a monoid with an inverse $g^{-1}$ for every element g. Thus G is a category with one objkect, in which every arrow is an isomorphismhom

**Theorem:** Every group G is isomorphic to a group of permutations
*Proof*

1. First, we will define the Cayley representation $\bar{G}$ of $G$ to be the following group of permutations: the underlying set of $\bar{G}$ is just $G$, and for each $g\in G$, we have the permutation $\bar{g}$, defined for all $h \in G$ by:
$$\bar{g}(h) = g \cdot h$$

Now check that $\bar{g} = \bar{h} \implies g = h$

$$\bar{g}(x) = g \cdot x$$
$$\bar{h}(x) = h\cdot x$$
$$\bar{g}(x) = \bar{h}(x) \implies g\cdot x = h\cdot x \equiv g=h$$

2. Yep, now we just define homomorphism $i: G \to \bar{G}$ by $i(g) = \bar{g}$ and  $j: \bar{G} \to {G}$ by $j(\bar{g}) = \bar{g}$

3. 
$$i\circ j \implies j(i(g)): G\to G\implies 1_{\bar{G}}$$
Likewise,
$$j\circ i \implies i(j(\bar{g})): \bar{G} \to \bar{G} \implies 1_G$$
Thus, we have shown that every group of G is isomorphic to a group of permutations
$$\blacksquare$$

**Theorem 1.6.** Every catergory $\mathbf{C}$ with a set of arrows is isomorphic to one in whic the objects are sets and the arrows are functions

*Proof*

* objects are sets of the form
$$\bar{C}  = \{f\in \mathbf{C} | \mathtt{cod}(f) = C\} \text{ s.t. } \forall C \in \mathbf{C} $$
* arrows are functions
$$\bar{g} : \bar{C} \to \bar{D}$$

for $g: C\to D$ in $\mathbf{C}$ defined by $\bar{g}(f) = g \circ f$ 

$$\blacksquare$$


