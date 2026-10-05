# Simple Retrosynthesis

A small rule-based retrosynthesis project built while learning Python and RDKit.

## About

This project started from a simple question:

> If I describe a chemical rule to a computer, can it actually do something with it?

The first version was intentionally simple. It does not use machine learning or deep learning. Instead, it translates manually defined retrosynthetic rules into runnable RDKit reaction templates.

## V0.1 — Amide Bond Cleavage

The first implemented reaction rule is retrosynthetic cleavage of an amide bond.

Given acetanilide:

`CC(=O)Nc1ccccc1`

the program applies a reaction SMARTS template and generates the corresponding fragments.

### Current reaction template

A simplified amide bond disconnection rule:

```text
[C:1](=O)[N:2] >> [C:1](=O)O.[N:2]
```

This is a deliberately simplified retrosynthetic rule rather than a complete model of chemical synthesis.

## Example

Input molecule:

Acetanilide

SMILES:

`CC(=O)Nc1ccccc1`

Applied rule:

Amide bond cleavage

Output:

Acyl fragment + Aniline fragment

## V0.2 — Multiple Reaction Templates

V0.2 expands the project from a single retrosynthetic rule to multiple manually defined reaction templates.

### Added

* Multiple reaction templates
* User-input SMILES
* Molecular structure visualization
* Reaction result visualization
* Basic reaction-template matching

The current templates include several simple transformations, such as:

* Amide bond cleavage
* Ester bond cleavage
* Acyl halide hydrolysis
* Anhydride hydrolysis
* Nitrile hydrolysis
* Alkyl halide substitution
* Alcohol chlorination
* Alcohol bromination

V0.2 also revealed an important limitation of a simple rule-based approach:

> A reaction rule can match a structure without necessarily representing a chemically reasonable or preferred transformation.

In other words:

**Being able to make a disconnection is not the same as knowing which disconnection should be made.**

This leads to the next question:

> If multiple transformations are possible, how should they be evaluated and ranked?

## Current Limitations

The current version is still a prototype.

It does not yet:

* reliably evaluate chemical feasibility
* rank candidate transformations
* learn from reaction datasets
* perform multi-step retrosynthesis
* use machine learning or deep learning

The current reaction templates are simplified prototypes for exploring how chemical rules can be translated into executable rules. A successful SMARTS match does not guarantee that the proposed transformation is chemically feasible, synthetically practical, or the most appropriate retrosynthetic choice.

## Why this project?

I am an undergraduate student studying Chinese Materia Medica and currently preparing for graduate school, with a particular interest in medicinal chemistry and computer-assisted synthesis.

This project is an attempt to connect organic chemistry with programming, starting from something small enough to actually build.

## Roadmap

* [x] Parse molecules with RDKit
* [x] Implement the first retrosynthetic rule
* [x] Add multiple reaction templates
* [x] Add basic molecular and reaction visualization
* [ ] Add candidate scoring
* [ ] Add basic chemical feasibility rules
* [ ] Add reaction/template statistics
* [ ] Explore machine-learning-based ranking
* [ ] Explore more advanced molecular representations

This project is primarily a learning and experimentation project.
