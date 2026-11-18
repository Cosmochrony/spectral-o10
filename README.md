This repository contains the source of the **O10** Cosmochrony paper  
*Projective Capacity on Heisenberg Graphs: Finite-Size Validation and Algorithmic Obstruction*.

This work extends the **spectral admissibility sub-programme** by performing the
first large-scale computation of projective capacity on polynomial-growth graphs,
following the geometric resolution established in **O9**.

While **O9** showed that Cayley graphs of the discrete Heisenberg group remove
the geometric obstruction identified in **O8**, it left open whether the capacity
exponent $\delta$ could be extracted in practice within this setting.

The present work addresses this question directly by implementing the
three-step permutation-path fingerprint on Heisenberg graphs at finite but
large prime $q$, and by evaluating the behaviour of the capacity observable
within the restored pre-saturation window.

The central object remains the **three-step permutation-path fingerprint** of O8,
evaluated here in the polynomial-growth regime identified in O9.

# Core Result

The paper establishes that the geometric obstruction identified in O8 is fully
resolved at the numerical level, but that a new limitation appears at the level
of representation and computation.

Starting from:

- the $k=3$ permutation-path fingerprint
- the O7 capacity observable $\Sigma_n$
- the O9 Heisenberg graph setting
- a dense TensorSketch implementation of the fingerprint

the analysis shows that:

- polynomial-growth behaviour is confirmed numerically:
    - growth exponent $\hat{D} \approx 3.05$ at $q = 101$
    - BFS depth scaling consistent with $\Theta(q)$
- a non-trivial pre-saturation window is observed:
    - $n^* = 13$ BFS steps at $q = 101$
    - capacity decay of $23.5\%$ across the window
- the state law $R_n^{(3)} \approx \Phi(\eta_n)$ remains valid
  at large $q$

However:

- the log-log regression yields $\hat{\delta} = 0.01$, which is not
  a reliable estimate of the capacity exponent
- reaching the power-law regime within $|B_n| \leq q^2$ would require
  a sketch dimension $D \gg q^4$, i.e.\ $D \gg 10^8$ at $q = 101$
- this renders dense TensorSketch-based extraction computationally impractical

Thus:

- the O8 geometric obstruction is resolved (O9 → O10)
- the fingerprint construction remains valid
- the remaining limitation is **algorithmic and representation-dependent**

# Structural Role of O10

O10 does not yet extract a value of $\delta$.

Instead, it establishes that the failure to measure $\delta$ is not due to:

- insufficient BFS depth
- or an absence of observable signal

but to:

- a mismatch between the dense fingerprint representation and the
  irreducible structure of the underlying dynamics

The logical chain is now:

- **O6**: fixed finite-dimensional fingerprints fail algebraically
- **O7**: the correct observable is projective capacity
- **O8**: exponential shell growth compresses the observable window
- **O9**: polynomial-growth graphs restore the window
- **O10**: dense fingerprint representations fail to resolve the
  compression regime

The obstruction is therefore no longer geometric, but algorithmic.

# What O10 Adds

O10 introduces several decisive results:

- the first large-$q$ computation of projective capacity on Heisenberg graphs
- numerical validation of:
    - polynomial shell growth
    - existence of a non-trivial pre-saturation window
    - persistence of the state law at large scale
- direct observation of **projective depletion** at large $q$
- identification of a new obstruction:
    - dense TensorSketch requires $D \gg q^4$ to access the asymptotic regime
- formulation of two distinct conditions for reliable exponent extraction:
    - sufficient geometric depth (satisfied in O9)
    - sufficient representation resolution (not satisfied here)

# Interpretation of the Result

The main conceptual outcome is the separation between:

- **geometry**, which determines the observable BFS depth
- **projective dynamics**, which determines the exponent $\delta$
- **representation level**, which determines whether the asymptotic regime
  can be accessed computationally

In particular:

- O9 shows that geometry must not compress the observable window
- O10 shows that geometry alone is not sufficient
- exponent extraction requires a representation aligned with the
  irreducible structure of the fingerprint

Thus, the obstruction to measuring $\delta$ is no longer structural in the
theory, but arises from the choice of computational representation.

# Relation to Previous Steps

O10 preserves all previous structural results:

- spectral admissibility from **Step 1**
- binary-polyhedral maximality from **Step 2**
- three-level ADE stratigraphy from **Step 3**
- projective dynamics and support contraction from **O1**
- hierarchical amplification via growing valence from **O3**
- structural upper bound on the cascade exponent from **O4**
- admissible-frontier saturation from **O5**
- fixed finite-dimensional no-go from **O6**
- capacity reformulation and state law from **O7**
- growing fingerprint and geometric obstruction from **O8**
- polynomial-growth resolution from **O9**

It does not modify the observable or the exponent to be measured.
Instead, it identifies the final obstruction preventing its extraction.

# Conceptual Structure

O10 advances the structural chain as follows:

1. Spectral admissibility → mode selection
2. Spectral capacity → binary-polyhedral maximality
3. Spectral stratigraphy → discrete ADE levels
4. O1 → ordering via support contraction
5. O3 → amplification via valence growth
6. O4 → structural upper bound on $\beta$
7. O5 → admissible-frontier saturation
8. O6 → fixed finite-dimensional no-go
9. O7 → projective capacity formulation
10. O8 → growing fingerprint + geometric obstruction
11. O9 → polynomial-growth geometry
12. O10 → finite-size validation + algorithmic obstruction

The programme now excludes:

- fixed finite-dimensional encodings
- exponential-growth graph geometries
- dense unstructured fingerprint compression

as viable settings for exponent extraction.

# What O10 Resolves

O10 provides:

- a full numerical validation of the Heisenberg setting at finite $q$
- confirmation that a measurable capacity signal exists
- a precise diagnosis of why exponent extraction fails in practice
- a separation between geometric and representation-level obstructions

# Residual Open Problem

What remains is no longer a question of geometry.

The remaining task is:

- constructing a representation-adapted fingerprint
- extracting $\delta$ in this aligned framework

This requires:

- decomposition of $\rho_{\mathrm{aff}}^{\otimes 3}$ into Weil blocks
- blockwise span tracking in dimension $O(q)$
- numerical validation across multiple primes

# Open Directions

1. **Weil-block fingerprint (O10-O1)**  
   Implement the blockwise decomposition and test exponent extraction

2. **Cross-prime extraction of $\delta$**  
   Measure the log-log slope for several Heisenberg primes

3. **Representation universality**  
   Test whether $\delta$ is stable across irreducible blocks

4. **Analytical derivation of $\delta$**  
   Derive the exponent from ADE representation theory

5. **Continuum connection**  
   Link discrete blockwise dynamics to the O7 capacity framework

# Status

This framework is now:

- free of algebraic obstruction (**O6**)
- free of geometric obstruction (**O8 → O9**)
- validated numerically at finite $q$ (**O10**)
- limited only by representation-level considerations

It does not assume:

- that geometric repair is sufficient for exponent extraction
- that dense sketches can access the asymptotic regime
- that finite-size signals directly yield reliable exponents

# Repository Structure
```
paper/
├── out/ # Compiled O10 PDF
├── tex/ # LaTeX sources
└── README.md
```

# Citation

If you reference this work, please cite:

J. Beau, *Projective Capacity on Heisenberg Graphs: Finite-Size Validation and Algorithmic Obstruction*, Zenodo, 2026.

# Acknowledgements

Portions of the derivations, conceptual synthesis, and editorial refinement
benefited from iterative interactions with large language models used as
analytical assistants.
All theoretical results and interpretations remain the sole responsibility
of the author.

# Contributions

This repository is intended as a research reference.

Critical feedback, independent verification, and alternative implementations
of representation-adapted fingerprints are welcome.

Please open an issue to discuss conceptual points,
technical details, or possible extensions.
