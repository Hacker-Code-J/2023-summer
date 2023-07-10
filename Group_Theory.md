 # Group Theory - Homomorphism

The multiplcative groups $\R^\times$ and $\C^\times$ are groups of non-zero real numbers and non-zero complex numbers under multiplcation, respectively. 

Assume that $\exists$ isomorphism $\phi:\R^\times\to\C^\times$. In the group $\R^\times$, every element except for $-1$ has an order of $1$ and $2$. This is because for every real number $r\neq -1$, either $r^1=r\neq 1$ or $r^2=1$ (in the case where $r=-1$).

 In the group $\C^{\times}$, however, there are elements of every order. For example, $i\in\C$ has an order of $4$, and there is no $n<4$ such that $i^n=1$.

---

The additive groups $(\mathbb{Z},+)$ (the group of integer) and $(\mathbb{Q},+)$ (the group of rational numbers) both under addition, are denoted as $G$ and $H$, respectively.

Assume that $\exist$ isomorphism $\phi:\mathbb{Z}\to\mathbb{Q}$. Consider an element $a\in\mathbb{Z}$ and its image $\phi(a)\in\mathbb{Q}$. Since
$$
\forall n\in\mathbb{Z}^+:\underbrace{a+a+\cdots+a}_{n\ \text{times}}=na\in \Z,
$$
the isomorphism would imply that
$$
\forall n\in\mathbb{Z}^+:\phi(na)=\underbrace{\phi(a)+\phi(a)+\cdots+\phi(a)}_{n\ \text{times}}=n\phi(a)\in\mathbb{Q}
$$
because $\phi$ preserves addition.

However, because $\mathbb{Q}$ is dense and $\mathbb{Z}$ is not, $\exists q\in\mathbb{Q}$ such that $\phi(a)<q<2\phi(a)$. Since $\phi$ is surjective, $\exists b\in\Z$ such that $q=\phi(b)$. But $\nexists n\in\Z$ s.t. $a<n<2a$, which contradicts the injectivity of $\phi$ because $b$ would map to some rational number strictly between $\phi(a)$ and $2\phi(a)$, yet no integer provides a corresponding "gap" in $\Z$.

Therefore, the additive groups $\Z$ and $\Q$ are not isomorphic.

---

**_Problem._** Let $G$ and $H$ be groups and let $\phi : G \to H$ be a homomorphism. Define the kernel of $\phi$ to be 
$$
\{g\in G : \phi(g) = 1_H\}
$$
Prove that the kernel of $\phi$ is a subgroup of $G$. Prove that $\phi$ is injective if and only if the kernel of $\phi$ is the identity subgroup of G. 

> **_Proof._**  
>
> 1. Proving that the kernel of $\phi$ is a subgroup of $G$:
>
> Let $\ker(\phi)$ be the kernel of $\phi$, so by definition,
> $$
> \ker(\phi)=\{g\in G:\phi(g)=1_H\}\subseteq G.
> $$
> To show that $\ker(\phi)\leq G$, we need to show that it satisfies the group axioms:
>
> - **_Closure_**: Let $a,b\in\ker(\phi)$, then
>
> $$
> \phi(ab)=\phi(a)\phi(b)=1_H1_H=1_H.
> $$
>
> Hence, $ab\in\ker(\phi)$.
>
> - **_Associativity_**: The operation in $\ker(\phi)$ is the same operation as in $G$ --- we do not define a new operation. Since the operation in $G$ is associative, the oeperation in any subset of $G$ (including $\ker(\phi)$) is also associative.
> - **_Identity_**: We know that $\phi(e_G)=e_H$. Hence $e_G$ be the identity of $\ker(\phi)$. 
> - **_Inverse_**: Let $a\in\ker(\phi)$ then
>
> $$
> \phi(a^{-1})=[\phi(a)]^{-1}=e_H^{-1}=e_H
> $$
>
> So, $\ker(\phi)\leq G$. 
>
> 2. Proving that $\phi$ is injective if and only if the kernel of $\phi$ is the identity subgroup of $G$:
>
> ($\implies$) Assume that $\phi$ is injective, that is,
> $$
> \forall g_1,g_2\in G:\phi(g_1)=\phi(g_2)\implies g_1=g_2.
> $$
> Consider the definition of the kernel $\ker(\phi)=\{g\in G:\phi(g)=1_H\}$. Since $\phi$ is injective, the only element in $G$ that can be mapped to $e_H$ is the identity $e_G$ itself. So, $\ker(\phi)$ must be, $\{e_G\}$, the identity subgroup of $G$.
>
> ($\impliedby$) Assume that the kernel of $\phi$ is the identity subgroup of $G$, that is, $\ker(\phi)=\{e_G\}$. Suppose for contradiction that $\phi$ is not injective. Then 
> $$
> \exists g_1,g_2\in G: \phi(g_1)=\phi(g_2)\land g_1\neq g_2.
> $$
> But then,
> $$
> \phi(g_1g_2^{-1})&=\phi(g_1)[\phi(g_2)]^{-1}\\
> &=\phi(g_1)[\phi(g_1)]^{-1}\\
> &=e_H.
> $$
> So $g_1g_2^{-1}\in\ker(\phi)$. But $g_1\neq g_2\implies g_1g_2^{-1}\neq e_G$, contradicting our assumption that $\ker(\phi)=\{e_G\}$. Hence $\phi$ is injective.
>
> 
>
> Therefore $\phi$ is injective if and only if the kernel of $\phi$ is the identity subgroup of $G$.



**_Problem._** Let $G$ be a group and let $Aut(G)$ be the set of all isomorphisms from G onto G. Prove that Aut( G) is a group under function composition (called the automorphism group of G and the elements of Aut( G) are called automorphisms of G). 

> **_Proof._** We want to show that the set $Aut(G)$ of all isomorphism form $G$ onto $G$ forms a group under function composition. Here are the group axioms we need to verify:
>
> - **_Closure_**: The composition of two isomorphisms is an isomorphism. This is a fundamental property of isomorphisms. So if $\phi$ and $\psi$ are in Aut(G), then so is their composition $\phi \circ \psi$.
>
> - **_Associativity_**: Function composition is associative, i.e., for any three functions (and therefore for any three isomorphisms) $\phi$, $\psi$, and $\omega$, we have $\phi \circ (\psi \circ \omega) = (\phi \circ \psi) \circ \omega$
>
> - **_Identity_**: The identity function $id: G\to G$, defined by $id(x) = x$ for all $x\in G$, is an isomorphism. It therefore serves as the identity element in Aut(G), because for any $\phi$ in Aut(G), we have $\phi \circ id = id \circ \phi = \phi$.
>
> - **_Inverse_**: The inverse of an isomorphism is also an isomorphism. If $\phi$ is in Aut(G), then $\phi^{-1}$ exists (since $\phi$ is an isomorphism, it is bijective, and thus has a well-defined inverse), and is in Aut(G). Moreover, $\phi \circ \phi^{-1} = \phi^{-1} \circ \phi = id$.
>
>   
>
>   Since Aut(G) satisfies these four properties, it is indeed a group under function composition. This group is called the automorphism group of G. Its elements, the automorphisms of G, are the isomorphisms from G onto itself.

