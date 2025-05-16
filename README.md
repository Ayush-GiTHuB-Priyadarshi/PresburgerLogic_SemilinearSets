# README for Presburger Logic and Semilinear Sets Repository

## Overview
This repository contains materials related to Presburger Arithmetic, semilinear sets, and their connections to automata theory . The content is based on a presentation titled "Presburger Logic and Semilinear Sets" .

## Table of Contents
1. [Introduction](#introduction)
2. [Key Concepts](#key-concepts)
3. [Presburger Arithmetic](#presburger-arithmetic)
4. [Semilinear Sets](#semilinear-sets)
5. [Automata-Based Construction](#automata-based-construction)
6. [Decidability](#decidability)
7. [Examples and Applications](#examples-and-applications)
8. [References](#references)

---

## Introduction
Presburger Arithmetic is the first-order theory of natural numbers with addition (but without multiplication). It is named after Mojżesz Presburger, who introduced it in 1929. This theory is decidable, unlike Peano Arithmetic, which includes both addition and multiplication and is undecidable.

This repository explores the foundations of Presburger Arithmetic, its limitations, and its connections to semilinear sets and automata theory. It also discusses the decidability of Presburger formulas and their applications in formal language theory.

---

## Key Concepts
### **Presburger Arithmetic: Axioms & Properties**  

#### **Language**  
- **Symbols**: `0`, `1`, `+`, `=`  
- **No multiplication** (weaker than Peano arithmetic).  

#### **Core Axioms**  
1. **Zero is minimal**: ¬(0 = x + 1)  
2. **Successors are unique**: x + 1 = y + 1 → x = y  
3. **Additive identity**: x + 0 = x  
4. **Addition is recursive**: x + (y + 1) = (x + y) + 1  
5. **Induction schema**: For any formula P(x),  
    (P(0) ∧ ∀x (P(x) → P(x+1))) → ∀y P(y)

*Unlike Peano arithmetic, Presburger’s lack of multiplication makes it decidable but less expressive.*

### Semilinear Sets
- **Definition**: A finite union of linear sets, where each linear set is defined by a base point and a set of periods.
- **Properties**: Closed under union, intersection, and complement.
- **Connection to Presburger Arithmetic**: Every semilinear set is definable in Presburger Arithmetic.

### Automata-Based Construction
- **Encoding**: Assignments of variables are encoded as binary strings.
- **Automata for Formulas**: Finite automata are constructed to accept satisfying assignments for atomic Presburger formulas.
- **Example**: Automaton for \( y = 2x + 1 \).

### Decidability
- **Presburger Arithmetic**: Decidable (there exists an algorithm to determine the truth of any Presburger formula).
- **Peano Arithmetic**: Undecidable (proven by Matiyasevich in 1970 as part of the solution to Hilbert's 10th problem).

---

## Presburger Arithmetic
### Syntax and Semantics
- **Terms**: Built using constants (0, 1), variables, and addition.
- **Formulas**: Atomic formulas (equality and inequality), combined with logical connectives and quantifiers.
- **Semantics**: Interpreted over natural numbers with addition and order.

### Limitations
- Cannot express non-linear terms like \( x . y \) or \( x^2 \).
- Cannot define properties like primality or divisibility.

---

## Semilinear Sets
### Definition
A subset of ℕⁿ is semilinear if it is a finite union of linear sets, where each linear set has the form:
- L(c; P) = { c + ∑ᵢ₌₁ᵏ aᵢpᵢ | aᵢ ∈ ℕ, pᵢ ∈ P }where \( c \) is a base point and \( P \) is a set of periods.

### Properties
- Closed under Boolean operations (union, intersection, complement).
- Equivalence with Presburger-definable sets.

### Non-Semilinear Example
The set X = {(x,y) ∈ ℕ² | y ≤ x²} is not semilinear.

---

## Automata-Based Construction
### Encoding Variables
Assignment Representation:
- Each variable assignment is encoded as a binary string
- Example: x ↦ 00101 (representing the value 5)

### Automata for Atomic Formulas
- Construct finite automata that accept satisfying assignments for atomic formulas.
- Example: For \( 2x + y - 3z = 2 \), the automaton checks the weighted sum of bits modulo 2 and transitions accordingly.

### State Bound
The number of states in the automaton is bounded by \( 2M + 2 \), where \( M \) depends on the coefficients of the formula.

---

## Decidability
### Presburger Arithmetic
- **Decidability**: There exists an algorithm to determine the truth of any Presburger formula.
- **Algorithm**: Based on quantifier elimination or automata-theoretic approaches.

### Peano Arithmetic
- **Undecidability**: No algorithm exists to decide the truth of arbitrary Peano Arithmetic formulas (solution to Hilbert's 10th problem).

---

## Examples and Applications
1. **Smallest Solution Example**: The equation \( (x + 2)^2 - 61y^2 = 1 \) has a smallest solution \( x = 1766319047, y = 226123980 \).
2. **Automata Construction**: Detailed steps for constructing automata for formulas like \( y = 2x + 1 \).
3. **Non-Semilinear Set**: Proof that X = {(x,y) ∈ ℕ² | y ≤ x²} is not semilinear.

---

## References
1. Ginsberg, S., & Spanier, E. H. (1964). *Bounded ALGOL-LIKE Languages*.
2. Ginsberg, S., & Spanier, E. H. (1996). *Semigroups, Presburger Formulas, and Languages*.
3. Wikipedia articles on:
   - [First-order Logic](https://en.wikipedia.org/wiki/First-order_logic)
   - [Hilbert's 10th Problem](https://en.wikipedia.org/wiki/Hilbert%27s_tenth_problem)
   - [Presburger Arithmetic](https://en.wikipedia.org/wiki/Presburger_arithmetic)
   - [Second-order Logic](https://en.wikipedia.org/wiki/Second-order_logic)

---
