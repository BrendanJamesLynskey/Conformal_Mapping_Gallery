# Conformal Mapping Gallery

**[Launch App](https://brendanjameslynskey.github.io/Conformal_Mapping_Gallery/)**

An interactive tool for exploring conformal mappings -- analytic functions of a complex variable that preserve angles at every point where the derivative is nonzero. Watch how grids, circles, and shapes warp under each transformation in real time.

## What is a conformal mapping?

A conformal map is a function f: C -> C that preserves the angle between any two curves at their point of intersection. In the z-plane you see a regular grid; in the w-plane you see the image of that grid under f(z). Notice that grid lines still meet at right angles even though they may become curves -- that is angle preservation in action.

## Mappings

| Mapping | Formula | Notes |
|---------|---------|-------|
| Squaring | w = z^2 | Doubles angles, squares distances |
| Cubing | w = z^3 | Triples angles, cubes moduli |
| Inversion | w = 1/z | Swaps inside/outside of unit circle |
| Exponential | w = e^z | Horizontal lines to rays, vertical to circles |
| Logarithm | w = log(z) | Inverse of exponential; branch cut on negative real axis |
| Sine | w = sin(z) | Maps strips to the plane; creates ellipses/hyperbolas |
| Cosine | w = cos(z) | Shifted sine |
| Blaschke factor | w = (z-a)/(1-conj(a)z) | Automorphism of the unit disc; drag a interactively |
| Joukowski | w = z + 1/z | Maps circles to airfoil shapes |
| General Mobius | w = (az+b)/(cz+d) | Fractional linear; maps circles/lines to circles/lines |
| Tangent | w = tan(z) | Poles at (n+1/2)pi |
| Square root | w = sqrt(z) | Halves the argument; branch cut on negative real axis |

## Features

- **Grid view** -- coloured grid lines in the z-plane mapped to curves in the w-plane
- **Domain colouring** -- every pixel coloured by the argument and magnitude of f(z)
- **Animation** -- smooth morph from identity (w = z) to the selected mapping
- **Unit circle tracking** -- see where the unit circle maps to
- **Fixed point markers** -- green dots mark fixed points of each mapping
- **Blaschke interaction** -- click and drag to position the parameter a inside the unit disc
- **Mobius parameters** -- enter complex values for a, b, c, d
- **Adjustable grid density and view range**
- **Responsive layout** for desktop and mobile

## Built with

- HTML5 Canvas for all rendering
- Vanilla JavaScript -- no dependencies, no build step
- Complex arithmetic implemented from scratch
- GitHub Pages for hosting
