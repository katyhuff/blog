---
layout: post
title: Cross Section Generation for Transient Analysis
comments: true
category: posts research atws
---

This is just a research microblogging post. It may be the last. 

Today, I'd like to instruct a graduate student on how to support some transient 
analysis with a temperature-dependent database of cross-sections for the 
various materials in the PB-FHR reactor.

## What Cross-sections Do We Need?

We want to achieve the same goals as the PBMR400 benchmark, but in the context 
of a different reactor design. That benchmark provides a full specification of 
26 energy group and temperature dependent cross sections. So, we probably want 
to do approximately the same thing.

## What Else Do We Need?
In addition to the cross sections, material properties are needed to conduct 
the transient analysis. The temperature, burn-up, and fluence dependencies of 
all thermophysical properties of the materials need to be defined. In our case, 
that includes : 

- FLiBe density, heat capacity, conductivity, etc.
- TRISO particle fuel matrix heat capacity, conductivity, etc.
- graphite density, heat capacity, etc. in the fuel pebbles and the reflectors

## What Tools Can Generate The Cross Sections?

Typically, Monte Carlo codes are the best at capturing geometries in nuclear 
reactors. Though the method is slower than many deterministic methods, monte 
carlo is the workhorse for cross section generation. Serpent and MCNP are the 
main options for this. Their merits are varied, but by virtue of being in C++ 
and being more user friendly for temperature dependent cross section 
generation, we've decided to go with Serpent. 

### Relying on Past Work

Past models of this reactor have been generated for MCNP by python scripts (see 
Cisneros, FIMPS, BEAU).  That work should be refactored into a python library 
for generating Serpent input as well. 

## What Else Do We Need to Consider?

When generating cross-sections, what else do we need to consider?

