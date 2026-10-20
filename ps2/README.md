# Problem Set 2 - Computational Macro

**Team Members:**

* Antonela Gjinaj
* Giovanni Manica

\---

## How to Run the Code

1. Ensure Julia is installed along with the required packages: `Plots`, `Printf`, `LinearAlgebra`, and `DataInterpolations`. If `DataInterpolations` is missing, uncomment and run the first cell of the notebook.
2. Open `ps2\\\\\\\_ag\\\\\\\_gm.ipynb`.
3. Run the cells from top to bottom.

\---

## Discussion Questions: Answers

### 2.2 (b)



The consumption error on the window falls with the number of asset points only for VFI on the grid (from 8.8e-2 to 2.1e-2) and for time iteration (from 2.5e-4 to 6.8e-6), because a denser grid reduces interpolation error. It does not fall for VFI off the grid (4.2e-6) and EGM (1.9e-5), which are bound by the stopping rule, and the maximum error on the whole grid stays at 1.8e-1 because it comes from the extreme boundary states. Regarding computational cost, the time per iteration of VFI on the grid scales roughly quadratically with the number of asset points (1.7, 6.5, 27.8 ms), whereas time iteration, EGM, and VFI off the grid scale roughly linearly, with EGM by far the cheapest.



### 2.2 (c):



Tightening the tolerances from 1e-6 to 1e-8 raises the iteration counts (for example 314 to 431 for VFI and 136 to 249 for EGM), and the effect on the consumption error differs by method. For VFI off the grid (4.2e-6 to 1.4e-7) and EGM (1.9e-5 to 2.3e-7) the error in (a) was set by the stopping rule. For VFI on the grid (4.6e-2 in both cases) and time iteration (4.6e-5 to 6.5e-5) it was set by the grid, since tightening the tolerance does not reduce it.



### 2.2 (d):



On the window, the maximum Euler error ranges from 7.9e-8 to 3.3e-6 and the mean log10 from -5.9 to -8.0 for the four accurate methods, while VFI on the grid is far worse (1.4e-2 and -2.2). Both measures rank the methods as Howard, VFI off the grid, EGM, time iteration, and VFI on the grid, but the Euler error is a residual of the first-order condition and not a distance to the exact policy. It understates the true error by one to two orders of magnitude (for EGM 8.1e-7 against e\_W = 1.9e-5), because errors in the policy that change the residual only slightly go unnoticed. States where a grid bound binds are excluded because there the Euler equation holds only as an inequality.



\---

### 3.2 (c):



By the Euler error, EGM is the most accurate (maximum 2.8e-6, mean log10 -6.9), followed by VFI off the grid and Howard (1.2e-4, -5.2), then time iteration (1.7e-4, -4.7) and VFI on the grid (2.5e-1, -1.8). I would trust EGM to about six or seven digits in the mean, VFI off the grid, Howard, and time iteration to about four or five, and not trust VFI on the grid. Since in 2.2 (d) the Euler error understated the true error by one to two orders of magnitude, and here no exact policy exists, these digits are an upper bound on the true accuracy.



\---

### 3.3:



At the lowest asset level the borrowing constraint binds at 2.0 % and 1.5 % of the grid points for the two lowest income states and at none for the others, which are the households that want to borrow. There the first-order condition holds only as an inequality, so the Euler errors are set to NaN and excluded from the statistics. The Euler equation error is largest just above the borrowing constraint, where the policy has its kink and the curvature is highest, so linear interpolation of the policy produces local approximation errors.



\---

## Note on AI Tools

* AI tools were consulted to assist with coding. All final outputs, implementations, and interpretations were thoroughly reviewed and verified.

