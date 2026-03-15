# Conformal Mapping Gallery

An interactive visualisation tool for exploring conformal mappings of the complex plane. Watch grids, circles, and domains warp in real time under twelve classical complex-analytic transformations, with full control over animation, grid density, view range, and colouring mode.

### [Launch App](https://brendanjameslynskey.github.io/Conformal_Mapping_Gallery/)

---

## What is a conformal mapping?

A **conformal map** is a holomorphic (complex-differentiable) function *f : C -> C* that preserves angles locally: wherever its derivative is nonzero, the angle between any two smooth curves passing through a point is the same as the angle between their images under *f*. In the app you see this directly -- the z-plane shows a regular grid whose lines meet at right angles, and the w-plane shows the image of that grid under the chosen mapping. The grid lines may bend into elaborate curves, yet they still intersect at 90 degrees everywhere the derivative is nonzero. That visual invariant is the hallmark of conformality.

Conformal mappings occupy a central place in both pure and applied mathematics. In **fluid dynamics**, every two-dimensional incompressible irrotational flow can be described by a conformal map; engineers exploit this to compute potential flow around obstacles and to design streamlined shapes. The **Joukowski transformation** (included in this gallery) maps circles to airfoil cross-sections and was one of the first analytic tools used in aerodynamics. In **electrostatics**, conformal maps transform simple boundary geometries into complex ones, making it possible to solve Laplace's equation in regions where direct methods would be intractable. Cartographers use conformal projections -- most notably the Mercator projection -- to map the curved surface of the Earth onto a flat chart while preserving local angles, which is critical for navigation.

The theoretical backbone is the **Riemann mapping theorem**: any simply connected open subset of the complex plane (other than the plane itself) can be conformally mapped onto the open unit disc. This profound result guarantees that conformal mappings exist in enormous generality, even when no closed-form formula is available. The twelve mappings in this gallery are the classical named transformations that *do* have explicit formulas, making them ideal for building geometric intuition about how complex functions reshape the plane.

## Mappings

| Mapping | Formula | Geometric effect | Significance |
|---------|---------|------------------|--------------|
| Squaring | *w = z*<sup>2</sup> | Doubles angles at the origin and squares distances from it. Two sheets of the z-plane fold onto one sheet of the w-plane. | Simplest nonlinear conformal map; illustrates branching and the loss of injectivity. |
| Cubing | *w = z*<sup>3</sup> | Triples angles and cubes moduli, producing three-fold rotational symmetry in the image. | Generalises squaring to higher-order power maps. |
| Inversion | *w = 1/z* | Swaps the inside and outside of the unit circle. Circles and lines map to circles and lines. | Self-inverse Mobius transformation; fundamental building block of more complex maps. |
| Exponential | *w = e<sup>z</sup>* | Sends horizontal lines to rays emanating from the origin and vertical lines to concentric circles. Maps the horizontal strip 0 < Im(z) < 2pi onto the punctured plane. | Connects additive and multiplicative structure of the complex numbers. |
| Logarithm | *w = log(z)* | Inverse of the exponential: circles map to vertical lines, rays to horizontal lines. Multi-valued, with a branch cut along the negative real axis. | Introduces the concept of branch cuts and Riemann surfaces. |
| Sine | *w = sin(z)* | Maps the vertical strip -pi/2 < Re(z) < pi/2 onto the complex plane minus two rays. Horizontal lines become ellipses; vertical lines become hyperbolas sharing the same foci. | Demonstrates how trigonometric functions extend to the complex plane. |
| Cosine | *w = cos(z)* | Similar to sine but phase-shifted. Vertical lines map to hyperbolas, horizontal lines to ellipses. | Complements sine; together they span the confocal conic family. |
| Blaschke factor | *w = (z - a) / (1 - a&#x0304;z)* | An automorphism of the unit disc: maps the disc onto itself, sending *a* to the origin while preserving the boundary circle. | Fundamental in complex analysis and signal processing. The parameter *a* can be dragged interactively. |
| Joukowski | *w = z + 1/z* | Maps circles passing near the unit circle into airfoil (wing) shapes. Critical points at z = 1 and z = -1 where the derivative vanishes. | Historically the first analytic method for computing lift on an airfoil; foundational in aerodynamics. |
| General Mobius | *w = (az + b) / (cz + d)* | The most general transformation that maps circles and lines to circles and lines. The four complex parameters a, b, c, d are user-configurable. | The Mobius group is the automorphism group of the Riemann sphere; every element is determined by where it sends three points. |
| Tangent | *w = tan(z)* | Poles at z = (n + 1/2)pi create a periodic lattice of singularities. Maps vertical strips to the plane. | Illustrates meromorphic behaviour and dense pole placement. |
| Square root | *w = sqrt(z)* | Halves the argument and takes the square root of the modulus. Branch cut along the negative real axis. | The simplest multi-valued algebraic function; inverse of squaring. |

## Features

- **Grid warping** -- A coloured rectangular grid is drawn in the z-plane (input domain) and its image under the selected mapping is drawn in the w-plane. Blue-family curves trace horizontal grid lines; pink/red-family curves trace vertical grid lines. Grid intersections remain at right angles wherever the mapping is conformal.
- **Domain colouring** -- Toggle from grid view to domain colouring mode, where every pixel is assigned a colour based on the argument (hue) and modulus (lightness banding) of *f(z)*. This reveals the full phase portrait of the function, including zeros, poles, and branch cuts.
- **Smooth animation** -- A parameter *t* in [0, 1] interpolates linearly between the identity map (*w = z*) and the selected conformal map. Press play to watch the grid continuously morph from flat to warped and back. The slider can also be dragged manually for frame-by-frame exploration.
- **Unit circle tracking** -- The unit circle is drawn on both planes so you can see exactly how it deforms under each mapping. Particularly illuminating for inversion and the Blaschke factor, where the circle maps to itself.
- **Fixed-point markers** -- Green dots on the w-plane mark the fixed points of each mapping (points where *f(z) = z*). These are annotated in the info bar below the canvases.
- **Blaschke interaction** -- When the Blaschke factor is selected, click and drag anywhere on the z-plane canvas to reposition the parameter *a* inside the unit disc. Sliders for modulus and argument are also provided.
- **Mobius parameters** -- When the General Mobius mapping is selected, four text fields appear where you can enter complex values for *a*, *b*, *c*, *d* (supporting formats like `1`, `-2.5`, `1+2i`, `-i`).
- **Joukowski airfoil** -- Select the Joukowski mapping and adjust the view range to see how circles of different radii and centres near the unit circle produce a family of symmetric and cambered airfoil profiles.
- **Adjustable grid density** -- A slider controls how many grid lines are drawn (from 5 to 40), letting you choose between a clean overview and fine structural detail.
- **Adjustable view range** -- A second slider scales the visible region of the complex plane from 0.5 to 6.0 units, so you can zoom in on local behaviour near the origin or zoom out to see large-scale structure.
- **Axis tick marks** -- Both canvases display numbered tick marks on the real and imaginary axes for easy coordinate reading.
- **Responsive layout** -- The two-canvas display stacks vertically on narrow screens and expands side-by-side on wider ones, with HiDPI / Retina support via devicePixelRatio scaling.

## Built with

- **HTML5 Canvas** for all rendering (grid lines, domain colouring, unit circle, fixed-point markers)
- **Vanilla JavaScript** -- zero dependencies, no build step, no frameworks
- **Complex arithmetic library** implemented from scratch (addition, multiplication, division, conjugation, exponential, logarithm, trigonometric functions, square root, arbitrary powers, linear interpolation)
- **GitHub Pages** for hosting
