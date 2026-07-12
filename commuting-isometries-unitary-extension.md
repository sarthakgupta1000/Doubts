# Commuting unitary extension of a commuting pair of isometries

## Statement

Let \(T,T'\in B(H)\) be isometries with \(TT'=T'T\). Then there exist a Hilbert space \(K\supset H\) and unitaries \(U,U'\in B(K)\) such that
\[
UH\subset H,\quad U'H\subset H,\qquad U\big|_H=T,\quad U'\big|_H=T',\qquad UU'=U'U.
\]
In other words, \((U,U')\) is a **commuting unitary extension** of \((T,T')\).

(The same conclusion holds for any family—finite or infinite—of mutually commuting isometries.)

---

## Ingredients

### Minimal unitary extension of one isometry

If \(V\in B(H)\) is an isometry, the Wold decomposition gives \(H=H_u\oplus H_s\) with \(V=V_u\oplus S\), where \(V_u\) is unitary and \(S\) is a unilateral shift with wandering subspace
\[
L=H_s\ominus SH_s=\ker S^*=\ker V^*\cap H_s.
\]
Identify \(H_s\) with \(\bigoplus_{n\ge 0}L\) so that \(S\) is the unilateral shift. Set
\[
K_s=\bigoplus_{n\in\mathbb{Z}}L
\]
and let \(\widetilde S\) be the bilateral shift on \(K_s\). Then
\[
U_V:=V_u\oplus\widetilde S
\]
on \(K_V:=H_u\oplus K_s\) is a unitary extension of \(V\), and it is **minimal** in the sense
\[
K_V=\bigvee_{n\in\mathbb{Z}}U_V^n H.
\]
Equivalently, \(K_V\) is spanned by vectors of the form \(U_V^n h\) with \(n\in\mathbb{Z}\) and \(h\in H\), and \(U_V^k\big|_H=V^k\) for all \(k\ge 0\).

---

## Explicit construction for the pair \((T,T')\)

### Step 1 — Unitary extension of \(T\)

Let \(U\) be the **minimal** unitary extension of \(T\) on
\[
\widetilde H=\bigvee_{n\in\mathbb{Z}}U^n H.
\]
Thus \(U\big|_H=T\) and \(U^k\big|_H=T^k\) for \(k\ge 0\).

### Step 2 — Commuting isometric extension of \(T'\) to \(\widetilde H\)

On the dense linear manifold of finite sums \(\sum_n U^n h_n\) (\(h_n\in H\), only finitely many nonzero), define
\[
\widetilde{T}'\Biggl(\sum_{n\in\mathbb{Z}}U^n h_n\Biggr)=\sum_{n\in\mathbb{Z}}U^n\,T'h_n.
\]

**Well-definedness / isometry.** For \(n\ge m\) and \(h_n,h_m\in H\),
\begin{align*}
\bigl\langle U^n T'h_n,\, U^m T'h_m\bigr\rangle
&=\bigl\langle U^{n-m}T'h_n,\, T'h_m\bigr\rangle
=\bigl\langle T^{n-m}T'h_n,\, T'h_m\bigr\rangle\\
&=\bigl\langle T'T^{n-m}h_n,\, T'h_m\bigr\rangle
=\bigl\langle T^{n-m}h_n,\, h_m\bigr\rangle
=\bigl\langle U^n h_n,\, U^m h_m\bigr\rangle,
\end{align*}
where we used \(U^{k}\big|_H=T^k\) (\(k\ge 0\)), commutativity \(TT'=T'T\), and that \(T'\) is isometric. The case \(m>n\) is symmetric. Hence \(\widetilde{T}'\) preserves inner products on a dense set and extends to an isometry on all of \(\widetilde H\). Clearly \(\widetilde{T}'\big|_H=T'\).

**Commutation with \(U\).** On the same dense set,
\[
\widetilde{T}'U\Biggl(\sum_n U^n h_n\Biggr)
=\widetilde{T}'\Biggl(\sum_n U^{n+1}h_n\Biggr)
=\sum_n U^{n+1}T'h_n
=U\widetilde{T}'\Biggl(\sum_n U^n h_n\Biggr),
\]
so \(\widetilde{T}'U=U\widetilde{T}'\).

**Unitary preservation.** If \(T'\) is already unitary, then \(\mathrm{Ran}\,\widetilde{T}'\) is dense in \(\widetilde H\) (because \(\mathrm{Ran}\,T'=H\) and \(\widetilde H=\bigvee_n U^n H\)), so \(\widetilde{T}'\) is unitary.

### Step 3 — Unitary extension of \(\widetilde{T}'\) (and of \(U\))

- If \(\widetilde{T}'\) is unitary, set \(K=\widetilde H\), \(U'= \widetilde{T}'\). Then \((U,U')\) is the desired commuting unitary extension.
- If not, let \(U'\) be the **minimal** unitary extension of \(\widetilde{T}'\) on
  \[
  K=\bigvee_{n\in\mathbb{Z}}(U')^n\widetilde H.
  \]
  Extend \(U\) to an operator \(\widetilde U\) on \(K\) by the same rule as in Step 2:
  \[
  \widetilde U\Biggl(\sum_{n\in\mathbb{Z}}(U')^n k_n\Biggr)=\sum_{n\in\mathbb{Z}}(U')^n\, U k_n
  \qquad(k_n\in\widetilde H).
  \]
  The same inner-product computation (now using that \(U\) is unitary, hence an isometry that already commutes with \(\widetilde{T}'\)) shows that \(\widetilde U\) is a well-defined **unitary** on \(K\) extending \(U\), and \(\widetilde U\,U'=U'\,\widetilde U\).

The pair \((\widetilde U,\,U')\) on \(K\supset H\) is a commuting unitary extension of \((T,T')\).

---

## Compact formula (Naimark / GNS view)

Equivalently, the \(\mathrm{B}(H)\)-valued kernel on \(\mathbb{Z}^2\)
\[
\Gamma\bigl((m,n),(m',n')\bigr)
=
\begin{cases}
T^{*(m'-m)}{T'}^{*(n'-n)} & \text{if }m'\ge m,\; n'\ge n,\\
\text{(the unique continuous extension forced by isometry + commutativity)} & \text{otherwise}
\end{cases}
\]
is positive definite (Brehmer’s condition holds automatically for two commuting isometries). The Naimark dilation of \(\Gamma\) produces a unitary representation \((m,n)\mapsto U^m{U'}^n\) of \(\mathbb{Z}^2\) on a larger space \(K\), whose generators \(U,U'\) restrict to \(T,T'\) on the copy of \(H\). The inductive construction above is an explicit realization of this dilation.

---

## Remarks

1. **Extension vs dilation.** For isometries, a unitary *dilation* is automatically a unitary *extension* (\(H\) is invariant under \(U\) and \(U'\), not merely co-invariant).
2. **Doubly commuting case.** If additionally \(T^*T'=T'T^*\), the Wold–Słociński decomposition
   \[
   H=H_{uu}\oplus H_{us}\oplus H_{su}\oplus H_{ss}
   \]
   reduces the problem to extending a unilateral shift (or a pair of doubly commuting shifts) to bilateral shift(s) coordinatewise; the inductive step is unnecessary.
3. **Contrast with contractions.** For commuting *contractions*, Andô’s theorem gives a commuting *unitary dilation* (not in general an extension). The construction above is special to isometries.
4. **Minimality.** One may always shrink \(K\) to
   \[
   K_{\min}=\bigvee_{m,n\in\mathbb{Z}}U^m{U'}^n H
   \]
   to obtain a minimal commuting unitary extension.

## References

- T. Andô, *On a pair of commutative contractions*, Acta Sci. Math. (Szeged) **24** (1963).
- B. Sz.-Nagy, C. Foiaş, H. Bercovici, L. Kérchy, *Harmonic Analysis of Operators on Hilbert Space*, Springer.
- T. Bhattacharyya, *Dilation of contractive tuples: a survey*, CMA Proceedings.
- Orr Shalit, *Topics in Operator Theory*, Lecture 3 (unitary extension of commuting isometries).
