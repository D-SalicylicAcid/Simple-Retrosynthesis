# Simple Retrosynthesis

A small rule-based retrosynthesis project built while learning Python and RDKit.

## About

This project started from a simple question:

> If I describe a chemical rule to a computer, can it actually do something with it?

The first version is intentionally simple. It does not use machine learning or deep learning. Instead, it translates a manually defined retrosynthetic rule into a runnable RDKit reaction template.

## V0.1 — Amide Bond Cleavage

The first implemented reaction rule is retrosynthetic cleavage of an amide bond.

Given acetanilide:

`CC(=O)Nc1ccccc1`

the program applies a reaction SMARTS template and generates the corresponding fragments.

### Current reaction template

```text
[C:1](=O)[N:2] >> [C:1](=O)O.[N:2]
```

This is a deliberately simplified retrosynthetic rule rather than a complete model of chemical synthesis.

## Current limitations

V0.1 can only demonstrate a single predefined reaction rule.

It does not yet:

* choose among multiple disconnections
* evaluate synthetic feasibility
* rank candidate routes
* learn from reaction datasets
* perform multi-step retrosynthesis
* use machine learning or deep learning

## Why this project?

I am an undergraduate student studying Chinese Materia Medica and currently preparing for graduate school, with a particular interest in medicinal chemistry and computer-assisted synthesis.

This project is an attempt to connect organic chemistry with programming, starting from something small enough to actually build.

## Roadmap

* [x] Parse molecules with RDKit
* [x] Implement the first retrosynthetic rule
* [ ] Add multiple reaction templates
* [ ] Add candidate filtering
* [ ] Add basic chemical feasibility rules
* [ ] Add reaction/template statistics
* [ ] Explore machine-learning-based ranking

This project is primarily a learning and experimentation project.
