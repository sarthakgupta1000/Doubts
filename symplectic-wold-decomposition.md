# Wold decomposition for a symplectic isometry: wandering space and the $J$-shift

**Question.** Let $H$ be a (real) symplectic Hilbert space, with the symplectic form
given by $\Omega(x,y)=g(Jx,y)$ for a compatible complex structure $J$. Let $T$ be a
linear map on $H$ that preserves $\Omega$. What is the Wold‑type decomposition of $H$
relative to $T$? What is the "wandering space", and what role does $J$ play (the
"$J$‑shift")?

**Answer.** If, in addition to preserving $\Omega$, $T$ is a genuine (metric) isometry
of $H$ — the natural symplectic analogue of a shift — then the classical Wold
decomposition applies to $T$ verbatim, and $J$ enters through exactly one new
structure: it identifies the symplectic defect space of $TH$ with $J(\text{wandering
space})$, and it makes $\Omega$, restricted to the shift part, into a **Toeplitz form**
whose symbol is a sequence of operators built from $J$ and $T$. This symbol sequence is
what we call the **$J$‑shift** of $T$. Below is a line‑by‑line construction and proof.

This continues `symplectic-extension-proof.md` (which treats a merely *bounded*
$\Omega$‑preserving $T$, without the isometry assumption): that document produces the
one‑step complement $H=R\oplus N$ topologically; the present note upgrades to a full
countable Wold decomposition once $T$ is also metrically isometric, and analyzes how
$J$ interacts with it.

---

## 0. Setup and notation

- $(H,g)$ — real Hilbert space, inner product $g$, norm $\|\cdot\|$.
- $J:H\to H$ — bounded linear, $J^{2}=-I$, $J^{*}=-J$. Equivalently ($J^{*}J=(-J)J=-J^2=I$)
  $J$ is $g$‑orthogonal: $\|Jx\|=\|x\|$ and $g(Jx,Jy)=g(x,y)$ for all $x,y$.
- $\Omega(x,y):=g(Jx,y)$ — the symplectic form. It is bounded ($|\Omega(x,y)|\le\|x\|\|y\|$),
  antisymmetric, and **strong**: the map $x\mapsto\Omega(x,\cdot)$ is a Banach‑space
  isomorphism $H\to H^{*}$ (composition of the Riesz isomorphism with the isomorphism
  $J$). See (P1)–(P3) of `symplectic-extension-proof.md` for the routine verifications.
- $T:H\to H$ is a **symplectic isometry**: a bounded linear map with
  $$\|Tx\|=\|x\|\quad\text{and}\quad \Omega(Tx,Ty)=\Omega(x,y)\qquad\text{for all }x,y\in H,$$
  equivalently $T^{*}T=I$ and $T^{*}JT=J$.

The prototype to keep in mind: $H=\bigoplus_{n\ge1}\mathbb R^{2d}$, $J=\bigoplus_n J_0$
($J_0$ the standard symplectic unit on $\mathbb R^{2d}$), and $T=S$ the right shift
$S(x_1,x_2,\dots)=(0,x_1,x_2,\dots)$.

---

## 1. A general duality: metric complements vs. symplectic complements

**Lemma 1.** For every closed subspace $M\subseteq H$,
$$M^{\perp_\Omega}:=\{v\in H:\Omega(v,M)=0\}\ =\ J\big(M^{\perp_g}\big),\qquad M^{\perp_g}:=\{v\in H:g(v,M)=0\}.$$

*Proof.*
1. $v\in M^{\perp_\Omega}\iff g(Jv,m)=0\ \forall m\in M\iff Jv\in M^{\perp_g}\iff v\in J^{-1}(M^{\perp_g})$.
2. $J^{2}=-I\Rightarrow J^{-1}=-J$, and for any linear subspace $S$ we have $-S=S$, so
   $-J(S)=J(-S)=J(S)$. Hence $J^{-1}(M^{\perp_g})=J(M^{\perp_g})$.
3. Combining 1–2 gives $M^{\perp_\Omega}=J(M^{\perp_g})$. $\blacksquare$

This holds for *any* closed $M$ — it uses nothing about $T$. It is the bridge between
the metric ($g$) and symplectic ($\Omega$) notions of "complement", and it is the only
place $J$ enters the construction below in closed form.

---

## 2. The metric Wold decomposition of $T$

This section is the classical Wold–von Neumann theorem (Halmos' proof), written out so
that Section 3 can refer to each step.

**Range closedness.** $R_1:=TH$ is closed: if $Tx_n\to z$ then $\|x_n-x_m\|=\|Tx_n-Tx_m\|\to0$
(isometry), so $x_n\to x$ for some $x\in H$, and $Tx=z$ by continuity; hence $z\in R_1$.
The same argument applied to the isometry $T^{n}$ shows $R_n:=T^{n}H$ is closed for every
$n\ge0$, and $R_{n+1}=T(R_n)\subseteq R_n$ (since $TH\subseteq H\Rightarrow T^n(TH)\subseteq T^n(H)$),
a decreasing chain of closed subspaces.

**Wandering space.** Define
$$N:=H\ominus TH=(TH)^{\perp_g}=R_1^{\perp_g}\qquad(\text{closed, since }R_1\text{ is closed}),$$
$$N_n:=T^{n}N\qquad(n\ge0),\qquad N_0=N.$$

**(W1) $T^{n}:N\to N_n$ is a linear isometry onto $N_n$.** $T^n$ is an isometry (a
composition of isometries), hence injective, and it maps the closed set $N$ onto the
closed set $N_n:=T^nN$ (closed by the same closed‑range argument as above); by
definition $\|T^na\|=\|a\|$ for $a\in N$.

**(W2) $N_n\perp_g R_{n+1}$.** Let $a\in N,\ r\in R_{n+1}=T^{n}(TH)$, say $r=T^{n}(Ts)$.
Then $g(T^{n}a,r)=g(T^{n}a,T^{n}(Ts))=g(a,Ts)=0$ (isometry preserves $g$; $a\in N=(TH)^{\perp_g}$,
$Ts\in TH$). Hence $g(T^na,r) = 0$, i.e. $N_n\perp_g R_{n+1}$.

**(W3) $R_n=R_{n+1}\oplus_g N_n$.** Given $h\in H$, write $h=w+a$ with $w\in TH,\,a\in N$
(orthogonal projection theorem, using that $TH$ is closed). Apply $T^{n}$:
$T^{n}h=T^{n}w+T^{n}a$, with $T^{n}w\in T^{n}(TH)=R_{n+1}$ and $T^na\in N_n$. So
$R_n=T^n H\subseteq R_{n+1}+N_n$; combined with (W2) this is the orthogonal decomposition
$R_n=R_{n+1}\oplus_g N_n$.

**(W4) $N_k\perp_g N_l$ for $k\ne l$.** If $l>k$ then $N_l\subseteq R_l\subseteq R_{k+1}$
(decreasing chain), and $N_k\perp_g R_{k+1}$ by (W2); hence $N_k\perp_g N_l$.

**(W5) Definitions of the two pieces.**
$$H_s:=\overline{\operatorname{span}}\Big(\bigcup_{n\ge0}N_n\Big)=\Big\{\textstyle\sum_{n\ge0}T^na_n:\ a_n\in N,\ \sum_n\|a_n\|^2<\infty\Big\},\qquad
H_\infty:=\bigcap_{n\ge0}R_n.$$
By (W1) and (W4), the map
$$\Psi:\ell^2(N)\to H_s,\qquad \Psi\big((a_n)_{n\ge0}\big)=\sum_{n\ge0}T^na_n$$
is a Hilbert space isomorphism (linear, onto by definition of $H_s$, and an isometry by
the Pythagorean theorem: $\|\Psi(a)\|^2=\sum_n\|T^na_n\|^2=\sum_n\|a_n\|^2$).

**(W6) $H=H_s\oplus_g H_\infty$.** *Orthogonality:* for $a\in N_n$ and $h\in H_\infty\subseteq
R_{n+1}$, (W2) gives $a\perp h$; since this holds for every $n$, $H_s\perp_g H_\infty$.
*Spanning:* fix $h\in H$. Iterating (W3), for every $n$ there are unique
$a_0,\dots,a_{n-1}\in N$ and $h_n\in R_n$ with
$h=h_n+\sum_{k=0}^{n-1}a_k$, and uniqueness of the orthogonal decomposition (W3) shows
the coefficients $a_k$ do not change as $n$ grows. Since the $a_k$ are pairwise
orthogonal, $\sum_{k<n}\|a_k\|^2=\|h\|^2-\|h_n\|^2\le\|h\|^2$, so $\sum_{k\ge0}\|a_k\|^2<\infty$;
put $a:=\sum_k T^ka_k\in H_s$. Then $h_n=h-\sum_{k<n}a_k\to h-a=:h_\infty$. For every
fixed $m$ and all $n\ge m$, $h_n\in R_n\subseteq R_m$ (closed), so the limit
$h_\infty\in R_m$; as $m$ was arbitrary, $h_\infty\in\bigcap_mR_m=H_\infty$. Thus
$h=a+h_\infty\in H_s+H_\infty$.

**(W7) $T|_{H_\infty}$ is a surjective isometry of $H_\infty$.**
*Invariance:* $T(H_\infty)=T(\bigcap_nR_n)\subseteq\bigcap_nT(R_n)=\bigcap_nR_{n+1}=H_\infty$.
*Onto:* let $h\in H_\infty$. Since $h\in R_1=TH$, there is (by global injectivity of $T$)
a **unique** $x\in H$ with $Tx=h$. For each $n$, $h\in R_{n+1}=T(R_n)$, so $h=Ty$ for some
$y\in R_n$; by uniqueness of the preimage, $y=x$, hence $x\in R_n$. As $n$ was arbitrary,
$x\in\bigcap_nR_n=H_\infty$ and $Tx=h$. So $T(H_\infty)=H_\infty$, and $T|_{H_\infty}$,
being an isometry onto itself, is a **unitary operator**.

**(W8) $T|_{H_s}$ is the unilateral shift of multiplicity $N$.** From
$\Psi(0,a_0,a_1,\dots)=\sum_{n\ge1}T^na_{n-1}=T\Big(\sum_{n\ge0}T^na_n\Big)=T\Psi(a_0,a_1,\dots)$,
i.e. $T\circ\Psi=\Psi\circ\Sigma$ where $\Sigma(a_0,a_1,\dots)=(0,a_0,a_1,\dots)$ is the
unilateral shift on $\ell^2(N)$. So $\Psi$ conjugates $T|_{H_s}$ exactly to $\Sigma\otimes I_N$.

> **Theorem A (Wold decomposition).** $H=H_s\oplus_g H_\infty$, both summands reduce
> $T$, $T|_{H_\infty}$ is unitary, and $T|_{H_s}\cong\Sigma\otimes I_N$ is a unilateral
> shift with wandering space $N=H\ominus TH$.

This is exactly Halmos' classical statement; nothing here has used $\Omega$ or $J$ yet.
They enter now.

---

## 3. Where $J$ enters: the symplectic defect and the $J$‑shift symbol

### 3.1 The symplectic defect space is $J(N)$

By Lemma 1 with $M=R_1=TH$,
$$R_1^{\perp_\Omega}=J\big(R_1^{\perp_g}\big)=J(N).$$
More generally, since (W3)/(W4) give $R_n^{\perp_g}=\bigoplus_{k<n}N_k$ (finite $g$‑orthogonal
sum, complement of $R_n$ in $H$), Lemma 1 gives, for every $n$,
$$R_n^{\perp_\Omega}=J\Big(\bigoplus_{k<n}N_k\Big)=\bigoplus_{k<n}J(N_k),$$
the last equality because $J$ preserves $g$ (Section 0), hence preserves orthogonality.
So **the symplectic wandering space $R_1^{\perp_\Omega}$ of $T$ is $J(N)$, not $N$
itself**: the metric wandering space and the symplectic defect space of $TH$ coincide up
to the fixed rotation $J$. (They are literally the same space only in the special case
$J(N)=N$.)

### 3.2 The Toeplitz structure of $\Omega$ on the shift part

For $a,b\in N$ and $k\ge0$ define the bounded bilinear form
$$\varphi_k(a,b):=\Omega(T^{k}a,b)=g(JT^ka,b),$$
equivalently the bounded operator
$$\Phi_k:=P_N\,J\,T^{k}\big|_N:N\to N,\qquad g(\Phi_ka,b)=\varphi_k(a,b),$$
where $P_N$ is the $g$‑orthogonal projection of $H$ onto $N$. Since $J$ and $T^{k}$ are
both $g$‑isometries, $\|\Phi_k\|\le1$ for every $k\ge0$; in particular $\Phi_0=P_NJ|_N$
is simply the **compression of $J$ to the wandering space**.

**Lemma 2 (reduction).** For $a,b\in N$ and $n\ge m\ge0$,
$$\Omega(T^na,T^mb)=\varphi_{n-m}(a,b).$$

*Proof.* Preservation of $\Omega$ by $T$ iterated $m$ times gives $\Omega(T^mx,T^my)=\Omega(x,y)$
for all $x,y\in H$. Take $x=T^{n-m}a,\ y=b$:
$\Omega(T^na,T^mb)=\Omega(T^m(T^{n-m}a),T^mb)=\Omega(T^{n-m}a,b)=\varphi_{n-m}(a,b)$. $\blacksquare$

By antisymmetry of $\Omega$, for $n<m$: $\Omega(T^na,T^mb)=-\Omega(T^mb,T^na)=-\varphi_{m-n}(b,a)$.

**Theorem B (the $J$‑shift form of $\Omega$).** Under the isomorphism
$\Psi:\ell^2(N)\to H_s$ of (W5), for $a=(a_n)_{n\ge0},\,b=(b_n)_{n\ge0}\in\ell^2(N)$,
$$\Omega\big(\Psi a,\Psi b\big)=\sum_{k\ge0}\sum_{m\ge0}\varphi_k(a_{m+k},b_m)\ -\ \sum_{k\ge1}\sum_{n\ge0}\varphi_k(b_{n+k},a_n),$$
where both double series are the (unconditionally convergent) values of
$$\lim_{N,M\to\infty}\ \sum_{n=0}^{N}\sum_{m=0}^{M}\Omega(T^na_n,T^mb_m),$$
which exists and equals $\Omega(\Psi a,\Psi b)$ because $\Omega$ is a bounded (hence
jointly continuous) bilinear form and $\Psi a=\lim_N\sum_{n\le N}T^na_n$,
$\Psi b=\lim_M\sum_{m\le M}T^mb_m$ in norm.

*Proof.* Split the finite double sum $\sum_{n\le N,m\le M}\Omega(T^na_n,T^mb_m)$ into
$n\ge m$ and $n<m$ and apply Lemma 2 to each term; letting $N,M\to\infty$ and
substituting $k=n-m$ (resp. $k=m-n$) gives the stated series. $\blacksquare$

We call the operator sequence $(\Phi_k)_{k\ge0}$, $\Phi_k=P_NJT^k|_N$, the
**$J$‑shift symbol of $T$**: it is exactly the extra data (beyond the shift $\Sigma$
itself) needed to reconstruct $\Omega$ on the pure‑shift part $H_s$. Theorem B says
$\Omega|_{H_s}$ is a **block‑Toeplitz form** with that symbol: the $(n,m)$ "matrix
entry" $\Omega(T^na_n,T^mb_m)$ depends only on $n-m$, exactly as for a Toeplitz operator
(compare `toeplitz-hankel-commutativity-note.md` in this repository, where the same
Toeplitz phenomenon appears for commutants of shifts).

### 3.3 Consistency check and the trivial‑symbol case

**Corollary.** $\varphi_0(a,b)=\Omega(a,b)$, i.e. $\Omega|_N$ is recovered from the
symbol at $k=0$, as it must be (take $n=m$ in Lemma 2).

**Example (the prototype has trivial symbol).** For $H=\bigoplus_{n\ge1}\mathbb R^{2d}$,
$J=\bigoplus_nJ_0$, $T=S$ the right shift: $N=$ the first block, $N_n=$ the $(n{+}1)$‑st
block, $H_\infty=\bigcap_nS^nH=\{0\}$ ($S$ is a *pure* shift). For $a\in N$ (a vector in
the first block), $S^{k}a$ lives entirely in block $k+1$; since $J$ is block‑diagonal,
$J S^{k}a$ also lives entirely in block $k+1$, so $P_N(JS^ka)=0$ for $k\ge1$ and
$P_N(Ja)=J_0a$ for $k=0$. Hence
$$\Phi_0=J_0,\qquad \Phi_k=0\ (k\ge1):$$
the symbol is trivial (concentrated at $k=0$), and Theorem B collapses to
$\Omega(\Psi a,\Psi b)=\sum_{n\ge0}g(J_0a_n,b_n)$ — the blocks are $\Omega$‑orthogonal
to each other, not just $g$‑orthogonal. This is special to $J$ being *adapted* to the
shift's block structure (each $N_n$ is $J$‑invariant). In general $\Phi_k\ne0$ for
$k\ge1$ measures exactly the failure of $J$ to be adapted to the filtration
$R_0\supseteq R_1\supseteq\cdots$ generated by $T$; equivalently, by §3.1, it measures
how far the symplectic defect space $J(N_n)$ is from lying inside a single $g$‑block
$N_n$.

---

## 4. Remarks

- **Where the isometry hypothesis is used.** Only §2 needs $T^{*}T=I$: it gives the
  Pythagorean identity that makes $H_s$ an *orthogonal* (not merely topological) direct
  sum and makes $\Phi_k$ uniformly bounded ($\|\Phi_k\|\le1$ for *every* $k$, not just
  $k=0$). Dropping isometry — keeping only boundedness and $\Omega$‑preservation — is
  exactly the situation of `symplectic-extension-proof.md`: one still gets $H=R\oplus N$
  with $R=TH$, but only as a topological (idempotent‑induced) direct sum with
  $\Omega(R,N)=0$, and iterating it produces a decomposition with growing (not
  uniformly bounded) norms $\|T^n|_N\|\le\|T\|^n$, so no Hilbert‑space ($\ell^2$) Wold
  decomposition in general — only the weaker "extension to a symplectic automorphism of
  a bigger space" proved there.
- **$T$ need not commute with $J$.** If $T$ did commute with $J$ (so $T$ is complex‑linear
  for the complex structure $J$), then $\Omega$‑preservation would be *automatic* from
  isometry alone: $\Omega(Tx,Ty)=g(JTx,Ty)=g(TJx,Ty)=g(Jx,y)=\Omega(x,y)$. The
  interesting case — where $\Omega$‑preservation is a genuinely extra hypothesis, and
  where the symbol $(\Phi_k)_{k\ge1}$ can be nonzero — is precisely when $T$ is a *real*
  (non‑complex‑linear) symplectic isometry, i.e. $TJ\ne JT$ in general; from
  $T^{*}JT=J$ and $TT^{*}=P_{TH}$ one gets $TJ=P_{TH}(JT)$, i.e. $JT-TJ$ takes values in
  $N=(TH)^{\perp_g}$ — a defect operator $\delta(x):=JTx-TJx\in N$, $x\in H$, which is
  the infinitesimal source of the nonzero symbol terms $\Phi_k,\ k\ge1$.
- **$H_\infty$ is again a symplectic Hilbert space.** $\Omega|_{H_\infty}$ is again a
  strong symplectic form (it is a restriction of a strong form to a subspace on which
  $T$ acts as a full symplectic automorphism, by the same idempotent argument as Step 2
  of `symplectic-extension-proof.md`), and $T|_{H_\infty}$ is a **symplectic unitary**
  (metrically unitary and $\Omega$‑preserving): the genuine "purely non‑shift"
  remainder of the decomposition.

$\blacksquare$
