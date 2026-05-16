# Fractal Ruler

🚧 TODO: outline for now

## 2 Subdivisions

- Like an [inch ruler](../case-studies/ruler.html)
- IFS with the following transformations:
    - $A(x) = (1/2)x$
    - $B(x) = (1/2)x + 1/2$

## 4 Subdivisions

- IFS with the following transformations:
    - $A(x) = (1/4)x$
    - $B(x) = (1/4)x + 1/4$
    - $C(x) = (1/4)x + 2/4$
    - $D(x) = (1/4)x + 3/4$

## N subdivisions 

- IFS with the following transformations
- $f_i(x) = (1/N)x + i/N$ for $i = 0, 1, ..., N-1$

## Other Notes

- I haven't mentioned what an IFS (iterated function system) is in this repo... I should make a note of that
    - and when I do, return to _Fractals Everywhere_ by Michael F. Barnsley, that covers the topic in depth
- How to explain why IFS iteration fills in the whole interval?
    - ❓Is this what mathematicians refer to as "dense" i.e. "the rationals are dense in the reals"?
    - The fractal addresses (when the functions are numbered with digits) are isomorphic to decimal expansions in base $N$
        - finite expansions -> rational numbers in base $N$
        - non-terminating expansions -> irrational numbers in base $N$
        - finite + infinite expansions -> real numbers in base $N$
    - This iterative process shows why e.g. 0.999... = 1.000... as the limit of both sequences