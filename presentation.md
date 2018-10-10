![](https://raw.githubusercontent.com/JuliaGraphics/julia-logo-graphics/master/images/three-balls.svg?sanitize=true) <!-- .element height="10%" width="10%" -->

# Julia

A new programming language *specifically* made for scientists and engineers.

Walks like Python, runs like C.


Note: ~5 years ago at MIT

---

# Two-language problem

Note: to build complex compiled programs OR to have fast dynamic programs, you have 2 languages involved

----

## Building compiled programs

1. Brain-storm in a dynamic language for algorithm exploration and testing.
2. Deliver a performant final-version in a compiled language.

Note: Most compiled programs had a testing stage in a dynamic language

----

## Using dynamic languages

```none
Does a package/library do exactly
what you need?
             ├── Yes:   Great!
             ├── Dunno: You need to read C/++ code.
             └── No:    You need to code in C/++.
```

Note: R, Python, and MATLAB are coded mostly in C/++. Anything that is fast in those languages is coded in C/++.

----

## What if the dynamic language was fast enough?

* [Benchmarks](https://julialang.org/benchmarks/)
* Solves the two-language problem
* `Julia` is mostly coded in `Julia`!

Note: Julia is mostly coded in Julia!


----


## LOC versus speed

![](https://raw.githubusercontent.com/johnfgibson/whyjulia/8b7617de701a25387e40dc00ee20ad99f4695c47/figs/ks_cpu_vs_lines_1024.png)

Note: The algorithm here is the KS-CNAB2 algorithm for numerical integration. Taken from https://github.com/johnfgibson/whyjulia/blob/master/1-whyjulia.ipynb


---

# Dynamic & fast, how?

1. Just-in-time compilation (JIT): User-level code is compiled to machine code on-the-fly.
2. Meticulous type system: Designed to maximize impact of JIT.
3. Multiple dispatch: Function dispatch determined at compile time when possible, run time when not.

Note: JIT compilation times are slow for first run


---

# Easy code

Looks like `Python`/`MATLAB`/`R` but with prettier syntax.


----

## Syntax

<section style="text-align: left;">
Math:
```julia
2π√3/5α₀
```
`Python`:
```python
2*np.pi*np.sqrt(3)/(5*alpha0)
```
`Julia`:
```julia
2π*√3/5α₀
```

Note: Unicode characters, degree symbol, Greek letters, square root, units. Easy to read and understand, scientists are not programmers.

----

## Custom infix operators

```julia
# rotate coordinate `c` by `θ` radians
julia> ↺(c, θ) = [cos(θ) -sin(θ); sin(θ) cos(θ)]*c
↺ (generic function with 1 method)

julia> [1,0] ↺ π/2
2-element Array{Float64,1}:
 0.0
 1.0
```

Note: This opens the door to tons of cool syntax.

----

## Embedded units

It took a beetle 36 seconds to walk 25 cm. How many days will it take it to walk 3 km?

```julia
using Unitful:uconvert, cm, km, s, d
v = 25cm/36s
t = 3km/v
uconvert(d, t)
```
5 days

Note: if you use m, cm, feet, degrees, radians, etc


---

# Missing

The concept of `missing` and `NaN` is treated correctly:
```julia
julia> NaN + 1         = NaN

julia> missing + 1     = missing

julia> true | NaN        ERROR!

julia> true | missing  = true

julia> false | missing = missing

julia> true & missing  = missing

julia> false & missing = false
```

Note: Consider that no other language has managed to get this concept of missing data correctly into their code.

---

# Zero overhead

Full access to all the libraries and functionalities you already know.

`MATLAB.jl`, `RCall.jl`, `PyCall.jl`, `JavaCall.jl`, `Mathematica.jl`, and `ccall` keyword to call `C` (and other languages, like `Fortran` and `Rust`)

Note: you can call Julia home without losing all of your furniture in the move.

---

# What I like about Julia

It is a modern language that makes your life easier.

----

## Some of my favourite things #1

* [QuantEcon](https://quantecon.org/): Provide lectures on models including code!
  - [QuantEcon.jl](https://quantecon.org/quantecon-jl), a package with most of the functionality that you need, e.g. [CompEcon.jl](https://github.com/QuantEcon/CompEcon.jl).
* [Parameters.jl](https://github.com/mauro3/Parameters.jl): Use parameters more comfortably.
* [Queryverse.jl](https://github.com/queryverse/Queryverse.jl): Like R's tidyverse? There is something similar in Julia!

Note: There are many more things as well. DataFrames are nice, Gladfly (Grammer of Graphics), Piping operator |>, etc.

----

## Some of my favourite things #2

* Macros aka meta programming:
  - Want to know how fast your function is? Use `@btime foo()`, it runs your function many times averaging durations. Also information about allocation of memory.
  - How to make your code faster? `@trace`
  - Want to see the machine code? `@code_native`

Note: It is easier to write good code in `Julia`, there is more guidance.

----

## Some of my favourite things #3

* `github` integration: your code and its documentation accessible to everyone.
  - You can view the code of packages you are using and read it (most likely written in Julia)!
* Makes it easy to contribute yourself. File issues with developers directly, bugs are quickly fixed.
* Discuss your problems with the growing Julia community on [discourse](https://discourse.julialang.org/).

Note: Sometimes even core developers chime in! Friendly experiences so far.

---

# Julia in economics

* `Julia` enjoys growing popularity - also in economics.
* The [NY FED ported their DSGE model](https://juliacomputing.com/case-studies/ny-fed.html) from `MATLAB` to `Julia` and it became a lot faster (up to 10x).
  - They also wrote a package: [DSGE.jl](https://github.com/FRBNY-DSGE/DSGE.jl)
* Mainly a substitute for [Dynare](http://www.dynare.org/) is missing - [Dolo.jl](https://github.com/EconForge/Dolo.jl) is offering [some](https://www.youtube.com/watch?v=bzBb9dtmfEc) of its functionality.
* [Here](https://www.sas.upenn.edu/~jesusfv/Update_March_23_2018.pdf) you can find a speed comparison of different programming languages in economics.

Note: More and more people are using Julia for their econ papers. If you have not invested heavily into `MATLAB` yet, you should give Julia a chance.

---

# Free & open source

* Easy to share and collaborate with *anyone*
* Drives the language forward
* Highly specialized and niche solutions and tools
* Free from hardware requirements
* No "black boxes", everything is within reach


Note: This is true for Python and R, but not MATLAB. Julia got git integration really well.

---

# Disadvantages
Mostly it's just too new…

Note: nothing is perfect.

----

## Too new!

* Ecosystems (e.g. packages, IDEs, debugger) not as mature as in other environments.
* Some of the more specialized libraries are missing.
* Harder to Google for answers.

Note: IDE (Integrated Development Environment). Maybe in 6 months or so the environment will solidify completely. Atom is, however, a really cool tool.

----

## Still working out all the kinks

* Loading some packages is still a bit slow.
* Plotting works but hasn't settled yet.
* Data analysis not yet as convienent as in `R`.
* Transitioning into `v1.0.0`: Major changes.

Note: Things missing are debuggers, viewers for dataframes, breaking points etc. I also managed so far without.

----

## General purpose

* Need statistics? `R`
* Need vectorized operations on matrices? `MATLAB`
* `Julia` (like `Python`) is more general-purpose → can be harder to find what you're looking for.
  - But if you can do it all in Julia - that's nice.

Note: apropos statistics, Douglas Bates, the developer of the `lme4` (Linear Mixed-Effects Models) R package for GLMMs switched to Julia.

---

# Conclusions

* `Julia` is considered by many one of the best dynamic languages out there.
* A number of libraries already far out-perform their equivalents in other languages.
* People come to `Julia` because of its speed, but stay for the type-dispatch system ♥
* Suffers from being "too new": might not be suitable for early adopters.

Note: I've started using Julia about two years ago and never looked back.


---

<!-- .slide: data-background-color="#ffffff" -->

![](https://raw.githubusercontent.com/JuliaGraphics/julia-logo-graphics/master/images/julia-logo.svg?sanitize=true) <!-- .element height="100%" width="100%" -->
