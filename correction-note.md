# Correction note for Bhuia's paper on constant characteristic functions

This note records the correction forced by the scalar regular-factorization
criterion in Sz.-Nagy--Foias theory.  In the paper, Theorem 2.2 is used as if,
for a scalar factorization

```math
\Theta=\Theta_2\Theta_1,
```

regularity implied the global alternative

```math
|\Theta_1(e^{it})|=1\text{ a.e.}\quad\text{or}\quad
|\Theta_2(e^{it})|=1\text{ a.e.}
```

The actual pointwise assertion is

```math
|\Theta_1(e^{it})|=1\quad\text{or}\quad |\Theta_2(e^{it})|=1
\quad\text{for a.e. }t.
```

Equivalently, if

```math
\Delta_j(t)=(1-|\Theta_j(e^{it})|^2)^{1/2},
```

then the scalar regularity condition is

```math
\Delta_1(t)=0\quad\text{or}\quad \Delta_2(t)=0
\quad\text{for a.e. }t,
```

not the assertion that one of the two functions is inner globally.

## 1. Correct scalar regular factorizations of a nonzero constant

Let

```math
c\in\mathbb C\setminus\{0\},\qquad |c|<1,\qquad
\alpha=(1-|c|^2)^{1/2}.
```

Let

```math
c=\psi\phi
```

be a scalar factorization by contractive analytic functions.  Since
`c` is nonzero, both factors are invertible in `H^\infty`.  The scalar
factorization is regular if and only if

```math
|\phi(e^{it})|=1\quad\text{or}\quad |\psi(e^{it})|=1
\quad\text{for a.e. }t.
```

Indeed, the dimension criterion quoted before Theorem 2.2 gives

```math
1=\mathbf 1_{\{\Delta_2>0\}}(t)+\mathbf 1_{\{\Delta_1>0\}}(t)
\quad\text{for a.e. }t,
```

because `\Delta=(1-|c|^2)^{1/2}` is strictly positive.  Thus exactly one of
`\Delta_1(t)` and `\Delta_2(t)` is nonzero for a.e. `t`, which is the pointwise
alternative above.

Since `|\phi(e^{it})||\psi(e^{it})|=|c|`, this is the same as saying that,
for a measurable set

```math
E=\{e^{it}:|\phi(e^{it})|=|c|\}
    =\{e^{it}:|\psi(e^{it})|=1\},
```

one has

```math
|\phi|=|c|,\ |\psi|=1 \quad\text{on }E,
```

and

```math
|\phi|=1,\ |\psi|=|c| \quad\text{on }\mathbb T\setminus E.
```

Thus

```math
\Delta_1=\alpha\chi_E,\qquad
\Delta_2=\alpha\chi_{\mathbb T\setminus E}.
```

The two scalar cases written in the paper correspond only to the extreme cases
`E=\mathbb T` and `E=\varnothing`.  They miss all nontrivial measurable splits.
For example, if `E` has measure strictly between `0` and `1`, the outer function
with boundary modulus `|c|` on `E` and `1` on `\mathbb T\setminus E`, together
with `\psi=c/\phi`, gives a regular scalar factorization that is not covered by
the paper's two scalar alternatives.

## 2. Corrected replacement for Theorem 3.3

Keep the model-space identification used in the paper:

```math
H_c=\left\{\left(f,-\frac{\bar c}{\alpha}f+h\right):
f\in H^2,\ h\in H^2_-\right\},
```

and

```math
T_c\left(f,-\frac{\bar c}{\alpha}f+e^{-it}g\right)
=
\left(e^{it}f-c\alpha g(0),
-\frac{\bar c}{\alpha}e^{it}f+g-\alpha^2g(0)\right).
```

Then the `T_c`-invariant subspaces are as follows.

### Scalar family

Let `c=\psi\phi` be any scalar regular factorization in the corrected sense
above.  Put

```math
\Delta_1=(1-|\phi|^2)^{1/2},\qquad
\Delta_2=(1-|\psi|^2)^{1/2},\qquad
E=\{\Delta_1>0\}.
```

Thus `\Delta_1=\alpha\chi_E` and
`\Delta_2=\alpha\chi_{\mathbb T\setminus E}`.  The corresponding invariant
subspace is

```math
Y_{\psi,\phi}
=
\left\{
\left(
\psi u,\,
-\frac{\bar c}{\alpha}\psi u
+P_-\big(\bar\phi\,\Delta_2u+v\big)
\right):
u\in H^2,\ v\in L^2(E)
\right\}.
```

Here `L^2(E)` denotes functions supported on `E`, and `P_+`, `P_-` are the
orthogonal projections of `L^2` onto `H^2` and `H^2_-`, respectively.

The paper's two scalar subspaces are recovered only as special cases:

* if `E=\mathbb T`, then `\psi` is inner and the formula reduces to

  ```math
  \left\{\left(\psi u,-\frac{\bar c}{\alpha}\psi u+h\right):
  u\in H^2,\ h\in H^2_-\right\};
  ```

* if `E=\varnothing`, then `\phi` is inner and the formula reduces to

  ```math
  \left\{\left(\psi u,-\frac{\bar c}{\alpha}\psi u
  +\alpha P_-(\bar\phi u)\right):u\in H^2\right\}.
  ```

### Vector family

The vector regular factorizations remain of the form used in the paper:

```math
\Theta_1=\binom{\theta_{11}}{\theta_{12}},\qquad
\Theta_2=(\theta_{21}\ \theta_{22}),
```

with

```math
|\theta_{11}|^2+|\theta_{12}|^2=1,\qquad
|\theta_{21}|^2+|\theta_{22}|^2=1,\qquad
\theta_{11}\theta_{21}+\theta_{12}\theta_{22}=c
```

a.e.  Put

```math
\beta_c=\theta_{11}\bar\theta_{22}-\theta_{12}\bar\theta_{21}.
```

Then `|\beta_c|=\alpha` a.e., and the corresponding invariant subspace is

```math
Y_{\Theta_2,\Theta_1}
=
\left\{
\left(
\theta_{21}u_1+\theta_{22}u_2,\,
-\frac{\bar c}{\alpha}(\theta_{21}u_1+\theta_{22}u_2)
+\alpha P_-\left((\bar\theta_{22}u_1-\bar\theta_{21}u_2)\beta_c^{-1}\right)
\right):
u_1,u_2\in H^2
\right\}.
```

This is the paper's item (3).

### Proof

Apply the Sz.-Nagy--Foias invariant-subspace theorem to the regular
factorization `c=\Theta_2\Theta_1`.

For a scalar factorization `c=\psi\phi`, the corrected regularity criterion gives
the pointwise alternatives encoded by `E`, `\Delta_1`, and `\Delta_2`.  Sickler's
scalar formula, written in the same representatives used in the paper, gives

```math
\{(\psi u,\bar\phi\,\Delta_2u+v):
u\in H^2,\ v\in L^2(E)\}.
```

Passing to the paper's representative in `H_c` sends a pair `(F,W)` to

```math
\left(F,-\frac{\bar c}{\alpha}F+P_-W\right),
```

which gives exactly the displayed formula for `Y_{\psi,\phi}`.

For vector regular factorizations, the paper's computation of `Z^{-1}` is still
valid:

```math
Z^{-1}(\Delta_2(w_1,w_2)\oplus0)
=
\frac{\alpha}{\beta_c}(\bar\theta_{22}w_1-\bar\theta_{21}w_2).
```

The same representative map then gives the displayed vector family.

These two families exhaust all invariant subspaces because the corrected
Theorem 2.2 allows only scalar regular factorizations with `dim F=1` and vector
regular factorizations with `dim F=2` when `c\ne0`.

## 3. Corrected proof for restrictions to invariant subspaces

The rank-two computation for `T_c` itself is unaffected.  The proof for
restrictions should, however, not be tied to the incomplete list of scalar
subspaces.

Let `Y` be any invariant subspace corresponding to a regular factorization

```math
c=\Theta_2\Theta_1.
```

The restriction part of the Sz.-Nagy--Foias factorization theorem shows that the
defect spaces of `S=T_c|Y` are controlled by the finite-dimensional coefficient
spaces appearing in the same regular factorization.  In the present setting these
spaces are the original one-dimensional defect space and the auxiliary space `F`,
where `dim F=1` in the scalar case and `dim F=2` in the vector case.  Consequently,

```math
\operatorname{rank}(I-S^*S)\le 1,\qquad
\operatorname{rank}(I-SS^*)\le \dim F\le 2.
```

Therefore

```math
S^*S-SS^*=(I-SS^*)-(I-S^*S)
```

has finite rank.  In particular, every restriction `T_c|Y` is essentially normal.
This proof covers the missing scalar regular factorizations as well as the vector
regular factorizations.

## 4. Corrected hyperinvariant-subspace statement

The final hyperinvariant-subspace statement must also be widened.  The
hyperinvariant subspaces are not merely the two scalar subfamilies displayed in
the paper; they are the invariant subspaces arising from scalar regular
factorizations in the corrected pointwise sense, namely the spaces
`Y_{\psi,\phi}` above.  Equivalently, one must allow all measurable splits `E`
for which

```math
|\phi|=|c|,\ |\psi|=1\text{ on }E,\qquad
|\phi|=1,\ |\psi|=|c|\text{ on }\mathbb T\setminus E.
```

The vector regular-factorization family gives invariant subspaces, but it is not
part of the scalar-factorization class singled out by Wu's hyperinvariant
subspace theorem.
