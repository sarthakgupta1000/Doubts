# Doubts

Mathematical notes and proofs.

## Symplectic commuting extensions

See [`symplectic-commuting-extensions.tex`](symplectic-commuting-extensions.tex) (and the compiled PDF) for a fully rigorous article proving:

1. **Single operator.** Every bounded symplectic embedding on a separable strong symplectic Hilbert space (e.g. \(\ell^2(\mathbb{N};\mathbb{R}^{2d})\) with \(\Omega=\bigoplus\omega_0\)) extends to a symplectic automorphism of a larger space, via an explicit defect construction.
2. **Commuting isometric pair.** Every commuting pair of *isometric* symplectic embeddings extends to a commuting pair of unitary symplectic automorphisms on a common enlargement (Itô conjugation on the minimal unitary dilation).

The non-isometric commuting-pair case is discussed in the final section: the elementary conjugation method does not close without isometry, though Krein-space dilation theory applies after complexification.

Compile with:
```bash
pdflatex symplectic-commuting-extensions.tex
pdflatex symplectic-commuting-extensions.tex
```
