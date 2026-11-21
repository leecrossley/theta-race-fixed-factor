# A fixed waiting factor for the 547/727 prime race

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.24410794.svg)](https://doi.org/10.5281/zenodo.24410794)

This result is now maintained in [theta-host-split-inert-race](https://github.com/leecrossley/theta-host-split-inert-race/tree/main/results/theta-race-fixed-factor). This repository is archived and keeps its releases and DOI.

Assume the generalised Riemann hypothesis (GRH) for the primitive Dirichlet $L$-functions in the 547/727 race and its base field, including the Riemann zeta function. **$`C=e^{175}`$ works after every starting height $`H\ge1`$.** In the 547/727 split–inert prime-ideal race with $`b=r=2`$, one doubling gains more than $`1.9735\log2`$ and another loses more than that. Both doublings start strictly after $`H`$ and finish before $`CH`$. The constant is about $`10^{76}`$.

For $`K=\mathbf Q(\zeta_{16})^+`$ the counted objects are prime ideals of $`K(\sqrt{397669})`$, classified by splitting in $`K(\sqrt{-547},\sqrt{-727})`$. Write $`S(y)`$ for the normalized inert-minus-split score on $`[y,4y]`$ with the tent weight and exclusions in the proof. A move runs from $`S(y)`$ to $`S(2y)`$. The result bounds both endpoints and permits either ordering. [Statement and proof](PROOF.md) · [Original theta trace](https://github.com/leecrossley/theta-race-short-shifts/blob/483c31f2df2132ed2165620ea55e20e969228bfb/RaceTrace.lean#L83)

The earlier deadline was $`e^{162000}H^{3001/2999}`$. The ratio of that deadline to $`H`$ grows with $`H`$. The gain comes from the GRH input. With no zeros off the line, a window of fixed log width suffices, whereas the earlier proof had to widen its window with $`\log H`$ to suppress possible off-line zeros above Platt's verified height. The present proof isolates a conductor-547 zero in a triangular averaging window of fixed log width. Two independent calculations bound the total contribution from all the other odd-factor zeros. Prime squares and higher powers fit within the remaining margin. [Earlier deadline](https://github.com/leecrossley/theta-race-waiting-bound/releases/tag/v1.0.0) · [Calculation output](evidence/check.txt)

The proof uses Alpöge's announced primitive Dirichlet GRH theorem. Sutherland's independent checks matched its formal statement, including the universal quantifier over primitive characters, and reported only the three standard Lean axioms. At the last update of that record (20 November 2026, 22:05 UTC), the Lean-kernel replay of the export and the lake comparator run were still in progress. No linear independence of zero ordinates is required. The analytic proof is written out. The local Lean file checks the numerical margin and the endpoint inequalities. The fixed-factor theorem and use of GRH are proved in the written argument. [Verification records](https://math.mit.edu/~drew/grh/) [Prior-work comparison](PRIOR-WORK.md)

The direct sieve gives factor 18 through one billion. Under the same GRH input, the factor $2e^6$ can miss a required move at arbitrarily large heights. [Two one-way windows](https://github.com/leecrossley/theta-race-factor-400/blob/f1773b07a55e76947d4e0c6ab19a112fd91fe6cf/PROOF.md) [Factor 18 and its obstruction](https://github.com/leecrossley/theta-race-factor-18/releases/tag/v1.0.1)

## Replay

With Python 3.10 or newer inside a virtual environment, install `requirements.txt` and run

```sh
python -m pip install -r requirements.txt
python fixed_bound.py
python poisson.py
python check_source.py
```

Run `bash verify-release.sh` for the complete x86-64 Linux replay. It requires Git, curl, tar and zstd. With Lean 4.33.1 on PATH and a built Mathlib at commit `0df444a360eaa60ab8c11dca51a86af692955474`, use `bash verify-release.sh /path/to/mathlib4`. A second optional argument supplies the directory of five already-downloaded upstream files listed in `check_source.py`. The replay checks the manifest, arithmetic, upstream evidence and compiled Lean module, then compares its output with the receipt. [Lean statements](FixedFactor.lean) · [File hashes](SHA256SUMS)
