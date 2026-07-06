# Extending a bounded symplectic map to a surjective one

**Question.** Let $T$ be a bounded linear map on $\ell^2(\mathbb{R}^{2d})$ that preserves
the symplectic form $\Omega=\bigoplus_n J$ (direct sum of the standard $2d\times 2d$
symplectic matrix $J$). Can $T$ be extended to a *bigger* symplectic space so that
the extension is **onto**?

**Answer. Yes, always.** Below is a line‑by‑line proof. It is the symplectic analogue
of the classical dilation of a Hilbert‑space isometry to a unitary; the prototype is
"the one‑sided shift extends to the two‑sided shift".

---

## Setup and notation

Everything works for any real separable Hilbert space carrying a *strong* symplectic
form; your $\ell^2(\mathbb{R}^{2d})$ is the special case $V=\bigoplus_n\mathbb{R}^{2d}$.

- $(V,g)$ — real Hilbert space, inner product $g$, norm $\|\cdot\|$.
- $\mathcal J$ — the complex structure $\mathcal J=\bigoplus_n J$. It satisfies
  $\mathcal J^2=-I$ and $\mathcal J^{*}=-\mathcal J$.
- $\Omega(x,y):=g(\mathcal J x,y)$ — the symplectic form.
- $T:V\to V$ — bounded linear, with $\Omega(Tx,Ty)=\Omega(x,y)$ for all $x,y\in V$.

We prove:

> **Theorem.** There exist a symplectic Hilbert space $(W,\hat\Omega)$ containing
> $(V,\Omega)$ as a symplectic subspace, and a bounded linear **bijection**
> $\tilde T:W\to W$ with bounded inverse, such that
> $\hat\Omega(\tilde T u,\tilde T v)=\hat\Omega(u,v)$ for all $u,v\in W$ and
> $\tilde T|_V=T$.

---

## Preliminary identities

**(P1) $\mathcal J$ is orthogonal, i.e. $\|\mathcal J x\|=\|x\|$.**
1. $\mathcal J^{*}\mathcal J=(-\mathcal J)\mathcal J=-\mathcal J^{2}=-(-I)=I$.
2. Hence $\|\mathcal J x\|^{2}=g(\mathcal J x,\mathcal J x)=g(x,\mathcal J^{*}\mathcal J x)=g(x,x)=\|x\|^{2}$.

**(P2) "Preserves $\Omega$" $\iff T^{*}\mathcal J T=\mathcal J$.**
1. $\Omega(Tx,Ty)=g(\mathcal J Tx,Ty)=g(T^{*}\mathcal J T x,\,y)$.
2. $\Omega(x,y)=g(\mathcal J x,y)$.
3. Equality for all $y$ $\iff T^{*}\mathcal J T x=\mathcal J x$ for all $x$ $\iff T^{*}\mathcal J T=\mathcal J$.

**(P3) $\Omega$ is a *strong* symplectic form.** Let $\iota_g:V\to V^{*}$ be the Riesz
isomorphism $\iota_g(x)=g(x,\cdot)$ and $\flat:V\to V^{*}$, $\flat(x)=\Omega(x,\cdot)$.
1. $\flat(x)=g(\mathcal J x,\cdot)=\iota_g(\mathcal J x)$, so $\flat=\iota_g\circ\mathcal J$.
2. $\iota_g$ and $\mathcal J$ are isomorphisms, hence so is $\flat$. (This is what "strong" means.)

---

## Step 1 — $T$ is bounded below (hence injective with closed range)

1. $T\neq0$: if $T=0$ then $\mathcal J=T^{*}\mathcal J T=0$ by (P2), contradicting $\mathcal J^{2}=-I$.
2. For every $x$:
   $\|x\|\overset{(P1)}{=}\|\mathcal J x\|\overset{(P2)}{=}\|T^{*}\mathcal J T x\|
   \le\|T^{*}\|\,\|\mathcal J Tx\|\overset{(P1)}{=}\|T\|\,\|Tx\|$.
3. Therefore $\|Tx\|\ge\dfrac{1}{\|T\|}\|x\|$ for all $x$: **$T$ is bounded below.**
4. Consequently $T$ is injective.
5. **Closed range.** Let $R:=T(V)$. If $Tx_n\to z$, then $(Tx_n)$ is Cauchy; by step 3
   $\|x_n-x_m\|\le\|T\|\,\|Tx_n-Tx_m\|$, so $(x_n)$ is Cauchy, $x_n\to x$, and by
   continuity $Tx=z$. Hence $z\in R$, so $R$ is closed.
6. Thus $T:V\to R$ is a bounded linear bijection onto the closed subspace $R$, with
   bounded inverse ($\|T^{-1}|_R\|\le\|T\|$).

---

## Step 2 — $\Omega|_R$ is again a strong symplectic form

1. $T:V\to R$ is a symplectomorphism: it is an isomorphism (Step 1.6) and
   $\Omega(Tx,Ty)=\Omega(x,y)$ by hypothesis.
2. Let $\flat_R:R\to R^{*}$, $\flat_R(r)=\Omega(r,\cdot)|_R$. For $r=Tx,\ s=Ty\in R$:
   $\flat_R(Tx)(Ty)=\Omega(Tx,Ty)=\Omega(x,y)=\flat(x)(y)$.
3. Writing $(T^{-1})^{*}:V^{*}\to R^{*}$ for the dual of the isomorphism
   $T^{-1}:R\to V$, step 2 says $\flat_R=(T^{-1})^{*}\circ\flat\circ T^{-1}$.
4. This is a composition of three isomorphisms ((P3) + Step 1.6), so $\flat_R$ is an
   isomorphism: **$\Omega|_R$ is strong** (in particular nondegenerate).

---

## Step 3 — Symplectic complement: $V=R\oplus N$ with $\Omega(R,N)=0$

Define the **defect space** $N:=R^{\perp_\Omega}=\{v\in V:\Omega(v,r)=0\ \forall r\in R\}$.

1. $N=\mathcal J^{-1}R^{\perp_g}$: indeed
   $\Omega(v,r)=g(\mathcal J v,r)=0\ \forall r\in R\iff \mathcal J v\in R^{\perp_g}\iff v\in\mathcal J^{-1}R^{\perp_g}$.
   In particular $N$ is closed (preimage of the closed set $R^{\perp_g}$ under the
   bounded invertible map $\mathcal J$).
2. Let $P_R$ be the $g$‑orthogonal projection onto $R$, and set $B:=P_R\mathcal J|_R:R\to R$.
3. $B$ is invertible on $R$: for $r,s\in R$,
   $g(Br,s)=g(P_R\mathcal J r,s)=g(\mathcal J r,s)=\Omega(r,s)=\flat_R(r)(s)$.
   Thus $B=\iota_R^{-1}\flat_R$ with $\iota_R$ the Riesz map of $R$; both factors are
   isomorphisms (Step 2), so $B$ is invertible.
4. Define $E:=B^{-1}P_R\mathcal J:V\to V$. It is bounded, and $E(V)\subseteq R$.
5. $E|_R=\mathrm{id}_R$: for $r\in R$, $Er=B^{-1}P_R\mathcal J r=B^{-1}(Br)=r$.
6. Hence $E^{2}=E$ (it maps into $R$ and fixes $R$) and $\operatorname{ran}E=R$.
7. $\ker E=N$:
   $Ev=0\iff P_R\mathcal J v=0$ ($B^{-1}$ injective) $\iff \mathcal J v\in R^{\perp_g}\iff v\in N$.
8. A bounded idempotent with range $R$ and kernel $N$ gives the **topological direct sum**
   $$V=R\oplus N,\qquad \Omega(R,N)=0\ \text{(by definition of }N).$$
9. $(N,\Omega|_N)$ is a strong symplectic Hilbert space:
   - *Nondegenerate*: if $n\in N$ and $\Omega(n,N)=0$, then also $\Omega(n,R)=0$, so
     $\Omega(n,V)=0$, hence $n=0$ by (P3).
   - *Strong*: given $\phi\in N^{*}$, set $\tilde\phi:=\phi\circ(I-E)\in V^{*}$; by (P3)
     there is $x=r+n\in V$ with $\Omega(x,\cdot)=\tilde\phi$. For $m\in N$,
     $\phi(m)=\Omega(r+n,m)=\Omega(n,m)$ (since $\Omega(r,m)=0$), i.e. $\flat_N(n)=\phi$.
     So $\flat_N:N\to N^{*}$ is onto, and it is injective by nondegeneracy.
10. $T$ is onto $\iff N=\{0\}$ (since $R=V\iff R^{\perp_\Omega}=0$). The enlargement is
    needed precisely when $N\neq\{0\}$.

---

## Step 4 — Construction of the bigger space $W$

1. Write $\omega:=\Omega|_N$ and take countably many isometric copies $N_1,N_2,\dots$ of
   $(N,\omega)$, with symplectic isometries $\iota_k:N\to N_k$
   (so $\omega(\iota_k a,\iota_k b)=\omega(a,b)$ and $\|\iota_k a\|=\|a\|$).
2. Define the Hilbert direct sum
   $$W:=V\ \oplus\ \bigoplus_{k\ge1}N_k
   =\Big\{(v;n_1,n_2,\dots):\ \|v\|^{2}+\textstyle\sum_k\|n_k\|^{2}<\infty\Big\},$$
   with inner product $\hat g$ the orthogonal direct sum.
3. Define the form
   $$\hat\Omega\big((v;n_\bullet),(v';n'_\bullet)\big):=\Omega(v,v')+\sum_{k\ge1}\omega(n_k,n'_k).$$
4. $\hat\Omega$ is bounded: by $|\Omega(v,v')|\le\|v\|\|v'\|$, $|\omega(n_k,n'_k)|\le\|n_k\|\|n'_k\|$
   and Cauchy–Schwarz, $|\hat\Omega(u,u')|\le\|u\|\,\|u'\|$.
5. $\hat\Omega$ is strong: the associated map $\hat\flat:W\to W^{*}$ is block‑diagonal,
   $\hat\flat=\flat\oplus\bigoplus_k\flat_N$; each block is an isomorphism ((P3), Step 2/3.9)
   and there are only finitely many distinct blocks ($\flat$ and $\flat_N$), so their
   inverses are uniformly bounded and $\hat\flat$ is an isomorphism.
6. Hence $(W,\hat\Omega)$ is a symplectic Hilbert space, and
   $V\hookrightarrow W,\ v\mapsto(v;0,0,\dots)$ is an isometric symplectic embedding onto
   the symplectic subspace $V\oplus0$.

---

## Step 5 — The extension $\tilde T$ and its verification

Define $\tilde T:W\to W$ by
$$\boxed{\ \tilde T(v;n_1,n_2,n_3,\dots)=\Big(\,Tv+\iota_1^{-1}n_1\ ;\ \iota_1\iota_2^{-1}n_2,\ \iota_2\iota_3^{-1}n_3,\ \dots\Big)\ }$$
i.e. $T$ acts on $V$, the copy $N_1$ is sent onto $N\subseteq V$ via $\iota_1^{-1}$, and each
$N_{k+1}$ is shifted onto $N_k$ via $\iota_k\iota_{k+1}^{-1}$.

**(a) Bounded.** Each map $\iota_1^{-1}$ and $\iota_k\iota_{k+1}^{-1}$ is an isometry, so
$$\|\tilde T u\|^{2}=\|Tv+\iota_1^{-1}n_1\|^{2}+\sum_{k\ge1}\|n_{k+1}\|^{2}
\le 2\|T\|^{2}\|v\|^{2}+2\|n_1\|^{2}+\sum_{k\ge1}\|n_{k+1}\|^{2}\le C\|u\|^{2}.$$

**(b) Extends $T$.** With $n_\bullet=0$: $\tilde T(v;0)=(Tv;0,\dots)$, i.e. $\tilde T|_V=T$.

**(c) Preserves $\hat\Omega$.** With $u=(v;n_\bullet),\ u'=(v';n'_\bullet)$,
$$\hat\Omega(\tilde Tu,\tilde Tu')=\Omega\big(Tv+\iota_1^{-1}n_1,\ Tv'+\iota_1^{-1}n'_1\big)
+\sum_{k\ge1}\omega\big(\iota_k\iota_{k+1}^{-1}n_{k+1},\ \iota_k\iota_{k+1}^{-1}n'_{k+1}\big).$$
Expand the first term using $Tv,Tv'\in R$, $\iota_1^{-1}n_1,\iota_1^{-1}n'_1\in N$ and $\Omega(R,N)=0$:
- $\Omega(Tv,Tv')=\Omega(v,v')$  (hypothesis);
- $\Omega(Tv,\iota_1^{-1}n'_1)=0$ and $\Omega(\iota_1^{-1}n_1,Tv')=0$  (since $\Omega(R,N)=0$);
- $\Omega(\iota_1^{-1}n_1,\iota_1^{-1}n'_1)=\omega(n_1,n'_1)$  ($\iota_1^{-1}$ symplectic).

The remaining sum equals $\sum_{k\ge1}\omega(n_{k+1},n'_{k+1})=\sum_{j\ge2}\omega(n_j,n'_j)$.
Adding up,
$$\hat\Omega(\tilde Tu,\tilde Tu')=\Omega(v,v')+\omega(n_1,n'_1)+\sum_{j\ge2}\omega(n_j,n'_j)
=\Omega(v,v')+\sum_{k\ge1}\omega(n_k,n'_k)=\hat\Omega(u,u').$$

**(d) Injective.** $\tilde T$ preserves the nondegenerate form $\hat\Omega$: if
$\tilde Tu=0$ then $\hat\Omega(u,u')=\hat\Omega(\tilde Tu,\tilde Tu')=0$ for all $u'$, so $u=0$.

**(e) Surjective.** Let $w=(z;m_1,m_2,\dots)\in W$. Solve $\tilde T u=w$:
- $N_k$‑components ($k\ge1$): $\iota_k\iota_{k+1}^{-1}n_{k+1}=m_k\Rightarrow n_{k+1}=\iota_{k+1}\iota_k^{-1}m_k$,
  and $\|n_{k+1}\|=\|m_k\|$, so $\sum_{k\ge1}\|n_{k+1}\|^{2}=\sum_k\|m_k\|^{2}<\infty$.
- $V$‑component: decompose $z=z_R+z_N$ with $z_R\in R$, $z_N\in N$ (Step 3). Put
  $v:=T^{-1}z_R$ (defined since $z_R\in R=\operatorname{ran}T$) and $n_1:=\iota_1 z_N$.
  Then $Tv+\iota_1^{-1}n_1=z_R+z_N=z$, with $\|v\|\le\|T^{-1}|_R\|\|z_R\|<\infty$.

Thus $u=(v;n_1,n_2,\dots)\in W$ satisfies $\tilde T u=w$. **$\tilde T$ is onto.**

**(f) Bicontinuous symplectomorphism.** $\tilde T$ is a bounded bijection of the Hilbert
space $W$, so by the bounded‑inverse theorem $\tilde T^{-1}$ is bounded; and
$\hat\Omega(\tilde T^{-1}a,\tilde T^{-1}b)=\hat\Omega(a,b)$ follows from (c). Hence $\tilde T$
is a symplectic automorphism of $W$.

$\blacksquare$

---

## The prototype

Let $S$ be the right shift on $V=\bigoplus_{n\ge1}\mathbb{R}^{2d}$,
$S(x_1,x_2,\dots)=(0,x_1,x_2,\dots)$. It preserves $\Omega=\bigoplus J$ and is an isometry,
but is **not** onto; here the defect space is $N=$ (the first $\mathbb{R}^{2d}$ block). The
construction above reproduces exactly the **two‑sided shift** on
$\bigoplus_{n\in\mathbb{Z}}\mathbb{R}^{2d}$, a symplectic bijection extending $S$.

## Remarks

- **Finite dimensions need no enlargement.** A symplectic map on $\mathbb{R}^{2m}$ has
  $(\det T)^2=1$, hence is already invertible. The phenomenon is genuinely
  infinite‑dimensional.
- **Where each hypothesis is used.** Boundedness of $T$ gives the bounded‑below estimate
  (Step 1) and thus closed range; strongness of $\Omega$ (automatic here since $\mathcal J$
  is orthogonal) gives the bounded symplectic projection $E$ (Step 3). Drop either and the
  clean complement can fail.
- **Analogy.** This is the symplectic version of the Wold / Sz.-Nagy–Halmos dilation of a
  Hilbert‑space isometry to a unitary, specialized so that the dilating operator preserves
  $\Omega=\operatorname{Im}\langle\cdot,\cdot\rangle$. The dilation built above is minimal.
