Partners: Antonela Gjinaj and Giovanni Manica

# Problem Set 1

## How to run

Exercise 1 is in `derivations.pdf`. For Exercise 2, open `ps1\_ex2.ipynb` in VS Code, select Julia, and run all cells in order. We used Julia 1.12.6 with `Plots` and `Printf`. If needed, install `Plots` by running `import Pkg; Pkg.add("Plots")` in Julia.

## Discussion

**2.1(f).** The policy meets the 45-degree line at about k = 2.8856, compared with k\* = 2.9208. The difference comes from restricting capital choices to grid points. The largest Euler error is at the bottom of the grid, where the policy is more curved and a given error matters more relative to consumption.

**2.2(a).** Starting from the grid point closest to 0.5k\*, the path settles at k = 2.885596. This is 0.035226 below the theoretical steady state.

**2.2(b).** Multiplying N by four reduces the maximum Euler error by factors of 3.62 and 4.11, consistent with O(N^-1). Runtime should grow roughly as O(N^2), since each step compares N choices at each of N states and the number of iterations changes little. The measured runtime factors are 21.68 and 13.72, compared with the predicted factor of 16; short-run timing variation helps explain the difference.

**2.2(c).** Our estimate is N = 800 \* (0.01110803 / 0.0001), or about 88,900 points. Using the final run's timing gives 1.011588 \* (88864.22 / 800)^2 = approximately 12,482 seconds, or 3.47 hours. This is an estimate based on the scaling above.

**2.2(d)-(e).** The economies with gamma = 1, 2, and 5 reach within 5% of k\* after 15, 22, and 37 periods. Their initial saving rates are 0.3163, 0.2543, and 0.1985. The gamma = 1 household gets there fastest: its higher intertemporal elasticity of substitution (1/gamma) makes it more willing to shift consumption across time, and it saves more initially. Higher gamma gives a lower elasticity and slower capital accumulation in these simulations.

## AI use

We used Claude for assistance with coding and for putting our handwritten solutions to Exercise 1 into a LaTeX file.

