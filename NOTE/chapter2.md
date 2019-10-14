# _Chapter 2 Context-Free Languages_
- [_Chapter 2 Context-Free Languages_](#_chapter-2-context-free-languages_)
  - [2.1 Context-Free Grammars (CFGs)](#21-context-free-grammars-cfgs)
    - [Definition](#definition)
    - [Ambiguity](#ambiguity)

## 2.1 Context-Free Grammars (CFGs)

### Definition
```
A context-free grammar is a 4-tuple (V, Σ, R, S), where
1. V is a finite set called the variables,
2. Σ is a finite set, disjoint from V , called the terminals,
3. R is a finite set of rules, with each rule being a variable and a
string of variables and terminals, and 4. S ∈ V is the start variable.
```
If u, v, and w are strings of variables and terminals, and A → w is a rule of the grammar, we say that `uAv yields uwv`, written `uAv ⇒ uwv`. <br/>
Say that `u derives v`, written `u ⇒∗ v`, <br/>
if u = v or if a sequence u1,u2,...,uk exists for k ≥ 0 and
u⇒u1 ⇒u2 ⇒...⇒uk ⇒v.

**Example:**
```
consider grammar G3 = ({S}, {a,b}, R, S). The set of rules, R, is
S →aSb|SS|ε.
This grammar generates strings such as abab, aaabbb, and aababb
```

### Ambiguity

**Ambiguous:** A string w is derived ambiguously in context-free grammar G if it has two or more different leftmost derivations. Grammar G is ambiguous if it generates some string ambiguously.

**Inherently ambiguous:** The context-free languages that can be generated only by ambiguous grammars are called inherently ambiguous.

**example:**

![](https://3.bp.blogspot.com/-iF2N3bfxoBA/VUBnQljjhII/AAAAAAAApds/RhDIFzQHC88/s1600/擷取3.PNG)