# Wold-type decomposition when $T$ is only symplectic (not an isometry)

**Follow-up question.** In `symplectic-wold-decomposition.md` we assumed $T$ is both an
isometry and $\Omega$-preserving. What survives if $T$ is *only* $\Omega$-preserving —
bounded, but not required to satisfy $\|Tx\|=\|x\|$?

**Answer, in one paragraph.** Everything that used only $\Omega$-preservation (not the
metric isometry) survives *unconditionally*: the wandering spaces $N_n$ built from the
symplectic complement, the filtration $R_n=T^nH$, the fact that $T$ carries $N_n$
isomorphically onto $N_{n+1}$, the pairwise $\Omega$-orthogonality of the $N_n$, and the
residual space $H_\infty=\bigcap_nR_n$ on which $T$ becomes a genuine symplectic
automorphism. What is lost is the *Pythagorean/orthogonal* assembly of these pieces into
a convergent $\ell^2$-sum — because that step used $\|T^na\|=\|a\|$. To get a literal
Hilbert-space direct sum back, one has to go through the **metric** wandering space
$W=H\ominus TH$ instead of the symplectic one, and invoke the Richter–Shimorin
theory of Wold decompositions for left-invertible (not necessarily isometric) operators,
as sharpened by Manolescu. We spell out exactly where the line is.

---

## 0. Setup

$(H,g,J,\Omega)$ as before: $\Omega(x,y)=g(Jx,y)$, $J^2=-I$, $J^*=-J$. Now
$$T:H\to H\text{ bounded, linear, with }\Omega(Tx,Ty)=\Omega(x,y)\ \ \forall x,y\qquad(\text{i.e. }T^{*}JT=J),$$
**with no assumption that $T$ is an isometry.**

**Running example (genuinely non‑isometric).** Take $d=1$, $J_0=\begin{psmallmatrix}0&-1\\1&0\end{psmallmatrix}$
on $\mathbb R^2$ (so $\Omega_0(u,v)=u_1v_2-u_2v_1$, the signed area), fix $\lambda>1$ and
let $T_0:=\operatorname{diag}(\lambda,\lambda^{-1})$. Since $\det T_0=1$, $T_0$ is
**symplectic** ($\Omega_0(T_0u,T_0v)=\Omega_0(u,v)$) but **not orthogonal**
($\|T_0e_1\|=\lambda\ne1$). Put $H=\bigoplus_{n\ge1}\mathbb R^2$, $J=\bigoplus_nJ_0$,
and
$$T(x_1,x_2,x_3,\dots):=(0,T_0x_1,T_0x_2,\dots)\qquad(\text{a "matrix‑weighted shift"}).$$
Then $\Omega(Tx,Ty)=\sum_ng(J_0T_0x_n,T_0y_n)=\sum_n\Omega_0(T_0x_n,T_0y_n)=\sum_n\Omega_0(x_n,y_n)=\Omega(x,y)$:
$T$ preserves $\Omega$. But $\|Tx\|^2=\sum_n\|T_0x_n\|^2\ne\sum_n\|x_n\|^2=\|x\|^2$ in
general: **$T$ is not an isometry.** We compute everything on this example as we go.

---

## 1. What Step 1–3 of `symplectic-extension-proof.md` still give (recap)

These three facts use **only** boundedness and $\Omega$‑preservation of $T$ — no
isometry — and are proved in that document; we cite them.

- **Fact 1 (bounded below).** $\|Tx\|\ge c\|x\|$ for all $x$, with $c:=1/\|T\|$. Hence $T$
  is injective and $R_1:=TH$ is closed.
- **Fact 2 (strength is inherited).** $\Omega|_{R_1}$ is again a strong symplectic form.
- **Fact 3 (one‑step complement).** $H=R_1\oplus N_0$ (a *topological*, i.e.
  bounded‑idempotent, direct sum — not $g$‑orthogonal), where
  $N_0:=R_1^{\perp_\Omega}=\{v:\Omega(v,R_1)=0\}$, $\Omega(R_1,N_0)=0$, $(N_0,\Omega|_{N_0})$
  is strong symplectic, and $T:H\to R_1$ is a bijective, bounded‑both‑ways
  symplectomorphism.

In the running example: $R_1=\{(0,y_1,y_2,\dots)\}$ (all of the "shifted‑off‑first‑block"
subspace, since $T_0$ is invertible), and $N_0=R_1^{\perp_\Omega}=J(R_1^{\perp_g})$
(Lemma 1 of `symplectic-wold-decomposition.md`, which used no isometry either) equals
$J_0(\text{first block})=\text{first block}$, since $J_0$ maps the first $\mathbb R^2$
block to itself. So $N_0=$ first block, exactly as in the isometric prototype.

---

## 2. The $\Omega$‑wandering filtration (unconditional — no isometry needed)

Define $R_n:=T^nH$ ($R_0=H$).

**Proposition 1.** For every $n\ge0$: $R_n$ is closed, $R_{n+1}\subseteq R_n$,
$\Omega|_{R_n}$ is strong, and $T:R_n\to R_{n+1}$ is a bijective, bounded‑both‑ways
symplectomorphism, with $\|Tx\|\ge c\|x\|$ on $R_n$ using the **same** constant
$c=1/\|T\|$ as on all of $H$.

*Proof (induction on $n$).* $n=0$ is Facts 1–3. For the inductive step, suppose the
statement holds at $n$; in particular $R_{n+1}=T(R_n)\subseteq R_n$ (this containment
also follows directly, without the inductive hypothesis, from $R_n\subseteq R_{n-1}\Rightarrow
T(R_n)\subseteq T(R_{n-1})$, i.e. $R_{n+1}\subseteq R_n$, by induction from $R_1\subseteq R_0=H$).
So $T$ restricts to a bounded, $\Omega|_{R_n}$‑preserving **self‑map** of the strong
symplectic Hilbert space $(R_n,\Omega|_{R_n})$ (its range is $R_{n+1}\subseteq R_n$).
Apply Facts 1–2 verbatim with $H$ replaced by $R_n$ and $T$ replaced by $T|_{R_n}$: since
$\|T|_{R_n}\|\le\|T\|$, Fact 1's bound $\|Tx\|\ge\|x\|/\|T|_{R_n}\|$ gives
$\|Tx\|\ge c\|x\|$ on $R_n$ with the same $c$; the closed‑range argument gives $R_{n+1}$
closed; Step 1.6‑type reasoning gives $T:R_n\to R_{n+1}$ bijective bounded‑both‑ways; and
Fact 2 gives $\Omega|_{R_{n+1}}$ strong. $\blacksquare$

Define, via Fact 3 applied to $(R_n,\Omega|_{R_n})$ and the self‑map $T|_{R_n}$,
$$N_n:=R_{n+1}^{\perp_\Omega\cap R_n}=\{v\in R_n:\Omega(v,R_{n+1})=0\},\qquad
R_n=R_{n+1}\oplus N_n\ (\Omega(R_{n+1},N_n)=0).$$

**Proposition 2 (the filtration is a genuine shift, at every finite level).**

**(a) $T(N_n)=N_{n+1}$, bijectively and bounded both ways.**

*$T(N_n)\subseteq N_{n+1}$:* let $v\in N_n$, so $v\in R_n$ and $\Omega(v,R_{n+1})=0$. Then
$Tv\in T(R_n)=R_{n+1}$. For any $t\in R_{n+2}=T(R_{n+1})$, write $t=Ts'$ with
$s'\in R_{n+1}$; then $\Omega(Tv,t)=\Omega(Tv,Ts')=\Omega(v,s')=0$ ($T$ preserves $\Omega$;
$s'\in R_{n+1}$ and $v\perp_\Omega R_{n+1}$). So $\Omega(Tv,R_{n+2})=0$, i.e. $Tv\in N_{n+1}$.

*$N_{n+1}\subseteq T(N_n)$:* let $w\in N_{n+1}\subseteq R_{n+1}=T(R_n)$. By bijectivity of
$T:R_n\to R_{n+1}$ (Prop. 1) there is a unique $v\in R_n$ with $Tv=w$; using the (unique)
decomposition $R_n=R_{n+1}\oplus N_n$ (Fact 3 at level $n$), write $v=r+\nu$ with
$r\in R_{n+1},\ \nu\in N_n$. Then
$$w=Tv=Tr+T\nu,\qquad Tr\in T(R_{n+1})=R_{n+2},\qquad T\nu\in T(N_n)\subseteq N_{n+1}$$
(the last inclusion by the direction just proved). But $R_{n+1}=R_{n+2}\oplus N_{n+1}$
(Fact 3 at level $n+1$) is also a **unique** decomposition, and $w\in N_{n+1}$ means
$w=0+w$ is *its* decomposition into an $R_{n+2}$‑part ($0$) and an $N_{n+1}$‑part ($w$).
Comparing the two decompositions of $w=Tr+T\nu$ forces $Tr=0$ and $T\nu=w$; since $T$ is
injective (Fact 1), $r=0$, so $v=\nu\in N_n$ and $Tv=w$. Hence $w\in T(N_n)$.

So $T(N_n)=N_{n+1}$, and this restriction of the bijection $T:R_n\to R_{n+1}$ (Prop. 1) is
itself bijective; it is bounded both ways because $T$ and $T^{-1}|_{R_{n+1}}$ are.

**(b) $N_n=T^n(N_0)$**, by induction from (a), and $T^n|_{N_0}:N_0\to N_n$ is a bijective,
bounded‑both‑ways, $\Omega$‑preserving isomorphism (a *symplectomorphism*, not a metric
isometry in general).

**(c) $\Omega(N_j,N_k)=0$ for all $j\ne k$** (full pairwise $\Omega$‑orthogonality — the
symplectic analogue of the wandering property, and it needs no isometry). *Proof:* say
$j>k$; then $N_j=T^j(N_0)\subseteq T^jH=R_j\subseteq R_{k+1}$ (decreasing chain, as
$j\ge k+1$), and $\Omega(N_k,R_{k+1})=0$ by definition of $N_k$; hence $\Omega(N_k,N_j)=0$,
and $\Omega(N_j,N_k)=-\Omega(N_k,N_j)=0$.

**(d) For every $n$: $H=R_n\oplus N_{n-1}\oplus\cdots\oplus N_0$**, a topological
(bounded‑idempotent) internal direct sum, obtained by iterating Fact 3's decomposition
$R_k=R_{k+1}\oplus N_k$ for $k=0,\dots,n-1$.

In the running example: $N_n=T^n(\text{first block})=\{(0,\dots,0,T_0^na,0,\dots):a\in\mathbb R^2\}$
sitting in block $n+1$; (c) holds trivially since different blocks are already
$g$‑orthogonal (hence $\Omega$‑orthogonal, as $\Omega$ is block‑diagonal too).

---

## 3. The residual space $H_\infty$ (also unconditional)

$$H_\infty:=\bigcap_{n\ge0}R_n.$$

**Theorem 1.** $T(H_\infty)=H_\infty$, and $T|_{H_\infty}$ is a bounded bijection with
bounded inverse — i.e. a **symplectic automorphism** of $(H_\infty,\Omega|_{H_\infty})$
(not necessarily metrically unitary).

*Proof.* $T(H_\infty)=T(\bigcap_nR_n)\subseteq\bigcap_nT(R_n)=\bigcap_nR_{n+1}=H_\infty$.
For surjectivity: let $h\in H_\infty\subseteq R_1=TH$. Because $T$ is **globally
injective** (Fact 1), there is a unique $x\in H$ with $Tx=h$. Fix $n$; since
$h\in R_{n+1}=T(R_n)$, there is $y\in R_n$ with $Ty=h$; by global injectivity $y=x$, so
$x\in R_n$. As $n$ was arbitrary, $x\in\bigcap_nR_n=H_\infty$, and $Tx=h$. So
$T(H_\infty)=H_\infty$. Boundedness of $T^{-1}$ on $H_\infty$ follows from Fact 1's global
bound $\|Tx\|\ge c\|x\|$, restricted to $x\in H_\infty$: this gives $\|T^{-1}h\|\le\|h\|/c$
for $h\in H_\infty$. $\blacksquare$

Nothing here used isometry — only injectivity and the bounded‑below estimate, both of
which came for free from $\Omega$‑preservation (Fact 1). In the running example
$H_\infty=\bigcap_nR_n=\{0\}$: $R_n$ is exactly "supported in blocks $>n$", and no
nonzero vector of $H=\bigoplus\mathbb R^2$ is supported past every finite block.

---

## 4. Exactly where isometry was needed, and what breaks without it

Combining §2–3: for every finite $n$ we have the decomposition (d) above, and
$H_\infty$ sits inside every $R_n$. The missing statement, compared to Theorem A of
`symplectic-wold-decomposition.md`, is the **infinite** one:
$$H\ \overset{?}{=}\ H_\infty\ \oplus\ \Big\{\textstyle\sum_{n\ge0}T^na_n: a_n\in N_0,\ \textstyle\sum_n\|a_n\|^2<\infty\Big\}.$$

The isometric proof of this (steps (W1)–(W6) in the earlier note) used $\|T^na\|=\|a\|$
in two places: (i) to get the Pythagorean identity $\|\sum_{n<K}T^na_n\|^2=\sum_{n<K}\|a_n\|^2$,
which needs the pieces to be **$g$‑orthogonal**, not just $\Omega$‑orthogonal; and (ii) to
make the resulting map $\Psi:\ell^2(N_0)\to H$ bounded. Without isometry we only have
$$c^n\|a\|\ \le\ \|T^na\|\ \le\ \|T\|^n\|a\|\qquad(a\in N_0),$$
(the lower bound from iterating Fact 1, the upper bound trivial) and **no** control on
$g(T^na,T^mb)$ for $a,b\in N_0$, $n\ne m$ — only on $\Omega(T^na,T^mb)$ (§2(c)). So
$\sum_nT^na_n$ need not converge for a general square‑summable $(a_n)$, and even when it
does, the norm of the sum is not $\sum\|a_n\|^2$.

**Concrete failure in the running example.** Take $a_n:=(1/n)\,e_1\in N_0\cong\mathbb R^2$
($n\ge1$; a genuinely $\ell^2$ sequence of scalars, $\sum(1/n)^2<\infty$). Then
$T^na_n$ lives in block $n+1$ with value $T_0^na_n=(\lambda^n/n)e_1$, so
$\|T^na_n\|=\lambda^n/n\to\infty$: the "obvious" sum $\sum_nT^na_n$ is **not even a
bounded sequence of partial sums**, let alone convergent. The isometric machinery of
`symplectic-wold-decomposition.md` genuinely cannot be run here.

---

## 5. Recovering an honest infinite decomposition: go metric, not symplectic

The fix in the literature (Richter, Shimorin, and — closest to what we need — Manolescu,
*Wold decomposition for operators close [to] isometries*, 2022) is to build the wandering
space out of the **metric** ($g$‑) orthogonal complement instead of the symplectic one,
because $g$‑orthogonal projections are automatically bounded by $1$ — no matter how much
$T$ distorts norms.

**Left invertibility.** $T$ bounded below (Fact 1) $\iff$ $T^{*}T$ is invertible $\iff$
$T$ has a bounded **left inverse** $T^{-}:=(T^{*}T)^{-1}T^{*}$ (so $T^{-}T=I$). This is a
completely general Hilbert‑space fact, independent of $\Omega$; here it is a *consequence*
of $\Omega$‑preservation via Fact 1.

**Metric wandering space.** $W:=H\ominus TH=\ker T^{*}$ (general fact, any bounded $T$).
By Lemma 1 of `symplectic-wold-decomposition.md` (valid for any closed subspace, in
particular $R_1=TH$, with no isometry needed):
$$N_0=R_1^{\perp_\Omega}=J\big(R_1^{\perp_g}\big)=J(W).$$
So **the base‑level relation between the metric and symplectic wandering spaces is
unconditional**: $N_0=J(W)$, always. (At higher levels $N_n=T^n(N_0)$ and $T^nW$ need not
correspond simply through $J$, unless $TJ=JT$ on the relevant subspaces — see the remark
at the end of `symplectic-wold-decomposition.md` on the defect operator $JT-TJ$.)

**The class $\mathcal D$ condition.** Following Manolescu (adapting Shimorin), say
$T\in\mathcal D$ if
$$(T^{n})^{-}=(T^{-})^{n}\qquad\text{for all }n\ge2.$$
This holds automatically if $T$ is an isometry ($T^-=T^*$ then, trivially). It also holds
for every bounded‑below **weighted shift** with weights bounded away from $0$ and
$\infty$ (a direct computation with the $e_k\mapsto w_ke_{k+1}$ basis; scalar version in
Manolescu §2), and more generally for **direct sums of operators in $\mathcal D$ acting on
$g$‑orthogonal summands** (block‑diagonal operators inherit $\mathcal D$ from their
blocks, since $T^{*}T$, $T^n$, and Moore–Penrose inverses are all computed blockwise).

**Theorem 2 (Manolescu 2022, Thm. 2.9–2.10, restated).** If $T\in\mathcal D$, then
$P_n:=T^{n}(T^{-})^{n}$ is the **$g$‑orthogonal projection** onto $R_n=T^nH$; $P_n$
converges strongly to the orthogonal projection $P_\infty$ onto $H_\infty=\bigcap_nR_n$;
and
$$H\ =\ H_\infty\ \oplus_g\ H_s,\qquad H_s:=\overline{\bigoplus_{n\ge0}}{}^{\,g}\,T^{n}W,$$
a genuine ($g$‑)orthogonal Hilbert‑space direct sum, with $H_\infty,H_s$ reducing $T$ and
$T|_{H_\infty}$ bijective. (In general $T|_{H_s}$ is only a *bounded‑below, bounded‑above
per‑summand* map $T^nW\to T^{n+1}W$ — a **weighted shift**, not literally conjugate to
$\Sigma\otimes I_W$ via an isometry, since as §4 shows there may be no bounded map
$\ell^2(W)\to H_s$ implementing $\sum a_n\mapsto\sum T^na_n$.)

**The running example is in $\mathcal D$.** In the standard coordinates $x=(x^{(1)},x^{(2)})$
per block ($x^{(i)}_n\in\mathbb R$), the block‑diagonal $T_0=\operatorname{diag}(\lambda,\lambda^{-1})$
makes $H=\bigoplus_n\mathbb R^2$ split $g$‑orthogonally as
$$H=\ell^2_{(1)}\oplus_g\ell^2_{(2)},\qquad \ell^2_{(i)}:=\{(x^{(i)}_n)_{n\ge1}\}\cong\ell^2(\mathbb R),$$
and $T=T^{(1)}\oplus T^{(2)}$ where $T^{(i)}$ is the scalar weighted shift with **constant**
weight $\lambda$ (resp. $\lambda^{-1}$): $T^{(1)}(x_1,x_2,\dots)=(0,\lambda x_1,\lambda x_2,\dots)$,
similarly $T^{(2)}$ with weight $\lambda^{-1}$. Each constant‑weight scalar shift is in
$\mathcal D$ (Manolescu's computation, specialized to $w_n\equiv$const), hence so is their
$g$‑orthogonal direct sum $T$. So Theorem 2 applies: $H=H_\infty\oplus_g H_s$ with (as
already found) $H_\infty=\{0\}$, so $H_s=H$ — consistent, since $W$'s images $T^nW$ (full
blocks $n+1$, as $T_0$ is onto $\mathbb R^2$) already exhaust $H$ $g$‑orthogonally; the
content of Theorem 2 here is exactly that this exhaustion is **genuinely orthogonal and
gives back all of $H$**, even though the per‑summand map $T^nW\to T^{n+1}W$ scales
vectors by wildly different factors ($\lambda^n$ on the $e_1$‑component, $\lambda^{-n}$ on
the $e_2$‑component) — precisely the "weighted shift, not unilateral shift" caveat above.

---

## 6. The Toeplitz / $J$‑shift symbol still makes sense (weaker bound, same formula)

Nothing in Lemma 2 of `symplectic-wold-decomposition.md` used isometry — only
$\Omega$‑preservation, iterated. So, verbatim: for $a,b\in N_0$ and $k\ge0$, set
$$\varphi_k(a,b):=\Omega(T^ka,b)=g(JT^ka,b),\qquad \Phi_k:=P_{N_0}JT^k\big|_{N_0},$$
($P_{N_0}$ the $g$‑orthogonal projection onto $N_0$; this projection is well defined and
bounded regardless of $T$). Then, exactly as before, for $n\ge m$: $\Omega(T^na,T^mb)=\varphi_{n-m}(a,b)$,
and for finite combinations $\sum_{n<K}T^na_n,\ \sum_{m<K}T^mb_m$ (which always make sense
as finite sums, no convergence issue),
$$\Omega\Big(\sum_{n<K}T^na_n,\sum_{m<K}T^mb_m\Big)=\sum_{n,m<K}\Omega(T^na_n,T^mb_m)$$
is the same block‑Toeplitz expression as Theorem B, term by term. The only casualty is the
**bound**: instead of $\|\Phi_k\|\le1$ we only get
$$\|\Phi_k\|\le\|J\|\,\|T^k|_{N_0}\|\le\|T\|^{k},$$
so the symbol can grow, and the formula is only guaranteed to describe $\Omega$ on the
**algebraic** (finite‑support) part of the filtration from §2, not on a completed
$\ell^2(N_0)$ — matching exactly the obstruction of §4.

In the running example: identical computation to before gives $\Phi_0=J_0$, $\Phi_k=0$
for $k\ge1$ (blocks are disjoint, $J$ block‑diagonal), regardless of $\lambda$ — the
symbol doesn't "see" the non‑isometry at all here, because the non‑isometric distortion
$T_0$ acts entirely *within* each $\Omega$‑orthogonal block and cancels out of
$\Omega(T^na,T^mb)$ for $n\ne m$ (which is $0$ either way, by disjoint supports).

---

## 7. Summary

| | $T$ isometric $+$ $\Omega$‑preserving | $T$ only $\Omega$‑preserving |
|---|---|---|
| Bounded below, closed range, $H=R\oplus N_0$ | ✅ (Facts 1–3) | ✅ (Facts 1–3, unconditional) |
| $\Omega$‑filtration $N_n=T^nN_0$, pairwise $\Omega(N_j,N_k)=0$ | ✅ | ✅ (§2, unconditional) |
| $H_\infty=\bigcap T^nH$: $T$ bijective, bounded inverse there | ✅ | ✅ (§3, unconditional) |
| Reduction formula $\Omega(T^na,T^mb)=\varphi_{n-m}(a,b)$ | ✅ | ✅ (§6, unconditional) |
| $H=H_\infty\oplus^g H_s$, genuine convergent $\ell^2$ sum, $T|_{H_s}\cong\Sigma\otimes I$ | ✅ automatically | only if $T\in\mathcal D$ (§5), and then with $g$‑, not $\Omega$‑, orthogonal pieces $T^nW$, and $T|_{H_s}$ a *weighted* shift |
| Symbol bound $\|\Phi_k\|\le1$ | ✅ | ✗ ($\le\|T\|^k$ only) |

$\blacksquare$
