# cnf
Definition:-
Conjunctive Normal Form is a way of structuring logical expressions in Boolean algebra. A formula is in CNF if it is a conjunction of one or more clauses, where each clause is a disjunction of literals. A literal is either a variable or the negation of a variable.

Example:
```Prolog
(A∨~B)∧(C∨D∨~E)
```
Here, ```Prolog(A∨~B)and(C∨D∨~E)``` are clauses, and the whole expression is in CNF.
# steps to convert to CNF
1. Eliminate implications and Bi-implications:
    * Replace A→B with ~A∨B.
    * Replace A↔B with (~A∨B)∧(~B∨A).
2. Move Negations Inward using De Morgan's Laws:
   * Apply De Morgan's laws to move negations inward, so that negations only apply to literals.
3. Distribute Disjunctions over Conjunction:
   * Apply distributive laws to achieve a conjuction of dijunctions (CNF form).
### Syntactic Proposition
    for ::= p         (proposition symbols)
    for | ~for        (negation)
    for | for ∧ for   (conjunction)
    for | for ∨ for   (disjunction)
    for | for --> for (implication)
    for | for <-> for (bi-implication)
# Usage
Load the module as usual in Prolog and then try the following. In the following examples, cnf is the function that normalizes to conjuntive normal form.

* cnf using De Morgan’s laws

```Prolog
cnf(a∨(b∧c),F).
cnf((a∧b)∨c,F).
```
* cnf remove double implication using equivalence

```Prolog
cnf(a<->b,F).
```
* cnf remove implication using equivalence

```Prolog
cnf(a-->b,F).
```
* cnf Denials internalized using equivalences

```Prolog
cnf(~(a-->b),F).
cnf(~(a∧b),F).
cnf(~(a∨b),F).
```
* cnf conjuntion elemental and

```Prolog
cnf(a∧b,F).
```
* cnf disjunction elemental or

```Prolog
cnf(a∨b,F).
```
* cnf of couple negation

```Prolog
cnf(~(~a),F).
```
* cnf of negation

```Prolog
cnf(~a,F).
```
* otherwise atomic PROP

```Prolog
cnf(a,F).
```


