This repository contains the source of the **O11** Cosmochrony paper  
[*Projective Capacity in Weil Blocks: First Reliable Extraction Strategy for the Capacity Exponent*](out/SpectralO11.pdf).

This work extends the **spectral admissibility sub-programme** by resolving the
last computational obstruction left open by **O10**, which prevented a reliable
log-log extraction of the projective-capacity exponent \(\delta\).

While **O10** showed that polynomial-growth Heisenberg graphs restore a genuine
pre-saturation window, it also established that the dense TensorSketch pipeline
remains computationally misaligned with the asymptotic regime of interest.
The problem is no longer geometric: it is now representation-theoretic and
algorithmic.

The present work removes this obstruction by replacing the dense
\(D \times q^2\) sketch by a **block-adapted fingerprint** built from the Weil
decomposition of the affine permutation representation.
This reduces the active span-tracking problem from a dense ambient space of
dimension \(q^2\) to irreducible blocks of dimension \(q\), where the
compression regime becomes numerically accessible.

The central object remains the **three-step permutation-path fingerprint** of O8,
but now expressed and propagated inside Weil-adapted blocks rather than inside a
global dense sketch.

# Core Result

The paper establishes that the obstruction identified in O10 is **not due to the
projective-capacity observable itself**, but to the mismatch between the dense
TensorSketch representation and the irreducible structure of the fingerprint.

Starting from:

- the \(k=3\) permutation-path fingerprint
- the O7 capacity observable \(\Sigma_n\)
- the O10 polynomial-growth Heisenberg background
- the decomposition of \(\rho_{\mathrm{aff}}^{\otimes 3}\) into Weil blocks

the analysis shows that:

- the active fingerprint decomposes into blocks of dimension \(O(q)\)
- span tracking inside a single block has per-vector cost \(O(q)\)
- the total blockwise capacity pipeline scales as \(O(q^4)\), rather than the
  prohibitive dense-sketch cost
- the pre-saturation window on Heisenberg graphs now contains enough BFS layers
  to support a meaningful log-log regression
- a reliable estimate of \(\delta\) requires two simultaneous conditions:
    - sufficient **geometric depth** in BFS steps
    - sufficient **effective span resolution** inside the active irreducible blocks
- these two conditions can fail separately:
    - they fail geometrically on LPS expanders (O8-O9)
    - they fail algorithmically in the dense TensorSketch regime (O10)
    - they become simultaneously attainable in the Weil-block regime

Thus:

- the O6 algebraic obstruction is bypassed (O8)
- the O8 geometric obstruction is removed (O9-O10)
- the O10 dense-sketch obstruction is removed (O11)
- the extraction of \(\delta\) becomes a genuinely testable quantitative problem

# Structural Role of O11

O11 is the first step in the programme whose purpose is not to identify a new
obstruction, but to provide the **first computationally viable route** toward a
reliable estimate of the capacity exponent.

The logical chain is now:

- **O6**: fixed finite-dimensional fingerprints fail algebraically
- **O7**: the correct observable is projective capacity
- **O8**: growing fingerprints restore a non-trivial signal
- **O9**: expander geometry compresses the observable window
- **O10**: polynomial-growth Heisenberg graphs restore the window, but the dense
  TensorSketch remains computationally misaligned
- **O11**: Weil-block fingerprints align the computation with the irreducible
  structure of the signal

O11 therefore does not merely improve performance.
It identifies the **correct representation level** at which exponent extraction
must be performed.

# What O11 Adds

O11 introduces several decisive structural results:

- a distinction between two independent necessary conditions for a reliable
  log-log estimate of \(\delta\):
    - **(C1) geometric depth condition**
    - **(C2) irreducible span-resolution condition**
- a proof that the dense TensorSketch regime is computationally non-viable for
  exponent extraction in the Heisenberg setting
- a blockwise reformulation of the fingerprint using Weil-adapted components
- a reduction of the active linear-algebra problem from ambient size \(q^2\) to
  block size \(q\)
- an explicit \(O(q^4)\) extraction strategy compatible with the
  pre-saturation window observed in O10
- the first setting in which a stable log-log slope can be meaningfully tested
  across several primes

# Interpretation of the Result

The main conceptual outcome is the separation between three distinct layers of
the problem:

- **graph geometry**, which controls how many BFS layers are observable
- **projective dynamics**, which controls the exponent \(\delta\)
- **representation alignment**, which controls whether the relevant compression
  regime can actually be measured

In particular:

- O9 showed that the graph family must not compress the observable window
- O10 showed that restoring the window is not sufficient
- O11 shows that the fingerprint must also be expressed in a representation
  basis aligned with its irreducible dynamics

Thus, a reliable estimate of \(\delta\) is possible only when both the geometry
and the representation level are correctly chosen.

# Relation to Previous Steps

O11 preserves all previous structural results:

- spectral admissibility from **Step 1**
- binary-polyhedral maximality from **Step 2**
- three-level ADE stratigraphy from **Step 3**
- projective dynamics and support contraction from **O1**
- hierarchical amplification via growing valence from **O3**
- structural upper bound on the cascade exponent from **O4**
- admissible-frontier saturation from **O5**
- fixed finite-dimensional no-go from **O6**
- capacity reformulation and state law from **O7**
- growing fingerprint from **O8**
- polynomial-growth geometric repair from **O9**
- finite-\(q\) Heisenberg validation and dense-sketch obstruction from **O10**

It does not change the observable or its target exponent.
Instead, it provides the first viable computational framework in which that
exponent can be extracted.

# Conceptual Structure

O11 advances the structural chain as follows:

1. Spectral admissibility → mode selection
2. Spectral capacity → binary-polyhedral maximality
3. Spectral stratigraphy → discrete ADE levels
4. O1 → ordering via support contraction
5. O3 → amplification via valence growth
6. O4 → structural upper bound on \(\beta\)
7. O5 → admissible-frontier saturation
8. O6 → fixed finite-dimensional no-go
9. O7 → projective capacity formulation
10. O8 → growing fingerprint
11. O9 → polynomial-growth geometry
12. O10 → finite-size validation + dense-sketch obstruction
13. O11 → Weil-block extraction framework for \(\delta\)

The programme now excludes both:

- fixed finite-dimensional encodings
- exponential-growth graph geometries
- dense unstructured fingerprint compression

as viable settings for exponent extraction.

# What O11 Resolves

O11 provides:

- a precise diagnosis of why the dense TensorSketch pipeline cannot yield a
  reliable \(\delta\)
- a block-adapted replacement aligned with the irreducible decomposition of the
  fingerprint
- a quantitative route from polynomial-growth geometry to actual exponent
  measurement
- the first framework where the log-log regression problem becomes
  computationally credible
- a clear separation between structural obstructions and implementation choices

# Residual Open Problem

What remains is no longer a question of graph family or computational ambient
dimension.

The remaining task is:

- performing the blockwise extraction of \(\delta\) at sufficiently large primes
- testing the stability of the measured slope across blocks and across \(q\)
- deriving the observed exponent from first principles

This requires:

- numerical implementation of the Weil-block fingerprint pipeline
- cross-prime regression analysis
- comparison of blockwise estimates for universality and stability

# Open Directions

1. **Cross-prime extraction of \(\delta\)**  
   Measure the log-log slope on several Heisenberg primes in the Weil-block regime

2. **Block universality**  
   Compare the exponent across different active Weil blocks

3. **Analytical derivation of \(\delta\)**  
   Derive the exponent from ADE representation theory and projective-capacity
   dynamics

4. **Higher-step fingerprints**  
   Test whether the blockwise strategy extends beyond the \(k=3\) fingerprint

5. **Continuum comparison**  
   Connect blockwise discrete measurements to the effective capacity framework of O7

# Status

This framework is now:

- free of algebraic obstruction (**O6**)
- free of geometric obstruction (**O8 → O9**)
- validated on polynomial-growth Heisenberg graphs (**O10**)
- expressed in a representation-adapted extraction framework (**O11**)

It does not assume:

- that geometric repair alone is sufficient
- that dense ambient sketches can reveal the asymptotic exponent
- that a visible finite-size signal automatically yields a reliable log-log slope

# Repository Structure
```text
paper/
├── out/ # Compiled O11 PDF
├── tex/ # LaTeX sources
└── README.md
```
# Citation

If you reference this work, please cite:

J. Beau, Projective Capacity in Weil Blocks: First Reliable Extraction Strategy
for the Capacity Exponent, Zenodo, 2026.

# Acknowledgements

Portions of the derivations, conceptual synthesis, and editorial refinement
benefited from iterative interactions with large language models used as
analytical assistants.
All theoretical results and interpretations remain the sole responsibility
of the author.

# Contributions

This repository is intended as a research reference.

Critical feedback, independent verification, and alternative blockwise
constructions for projective-capacity extraction are welcome.

Please open an issue to discuss conceptual points,
technical details, or possible extensions.
