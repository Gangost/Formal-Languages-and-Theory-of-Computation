# _Chapter 4 Decidability_
- [_Chapter 4 Decidability_](#_chapter-4-decidability_)
  - [Decidable Languages](#decidable-languages)
    - [Decidable Problems Concerning Regular Languages](#decidable-problems-concerning-regular-languages)
    - [Decidable Problems Concerning Context-Free Languages](#decidable-problems-concerning-context-free-languages)
  - [The Halting Problem](#the-halting-problem)
    - [AN UNDECIDABLE LANGUAGE](#an-undecidable-language)
    - [A TURING-UNRECOGNIZABLE LANGUAGE](#a-turing-unrecognizable-language)

## Decidable Languages

### Decidable Problems Concerning Regular Languages

A<sub>DFA</sub> ={⟨B,w⟩ | B is a DFA that accepts input string w}

A<sub>NFA</sub> ={⟨B,w⟩ | B is an NFA that accepts input string w}

A<sub>REX</sub> = { ⟨R, w⟩ | R is a regular expression that generates string w }

E<sub>DFA</sub> ={⟨A⟩ | AisaDFAandL(A)=∅}

EQDFA ={⟨A,B⟩ | AandBareDFAsandL(A)=L(B)}

### Decidable Problems Concerning Context-Free Languages

A<sub>CFG</sub> ={⟨G,w⟩ | G is a CFG that generates string w}

E<sub>CFG</sub> ={⟨G⟩ | G is a CFG and L(G)=∅}

EQ<sub>CFG</sub> ={⟨G,H⟩ | G and H are CFGs and L(G)=L(H)}<br/> EQ<sub>CFG</sub> is **UNDECIDABLE**

## The Halting Problem

A<sub>TM</sub> ={⟨M,w⟩ | M is a TM that accepts w}

A<sub>TM</sub> is undecidable.


### AN UNDECIDABLE LANGUAGE

![](https://3.bp.blogspot.com/-D4ZPjpMudeo/VVDFlZ_ETTI/AAAAAAAAplM/UHW-E4nmIuM/s400/fXjhV.png)

### A TURING-UNRECOGNIZABLE LANGUAGE

A language is decidable iff it is Turing-recognizable and co-Turing-recognizable.