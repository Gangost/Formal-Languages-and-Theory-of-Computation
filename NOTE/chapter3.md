# _Chapter 3 The Church-Turing Thesis_

- [_Chapter 3 The Church-Turing Thesis_](#chapter-3-the-church-turing-thesis)
  - [3.1 Turing Machines](#31-turing-machines)
    - [Formal Definition of A Turing Machine](#formal-definition-of-a-turing-machine)
    - [Example:](#example)

## 3.1 Turing Machines

Finite control + unlimited and unrestricted memory.

1. Write on the tape and read from it.
2. Move the head to the left and to the right.
3. The tape is infinite.
4. Reject and accept immediately.

### Formal Definition of A Turing Machine

A Turing machine is a 7-tuple (Q, Σ, Γ, δ, q0, qaccept, qreject), where Q, Σ, Γ are all finite sets and

1. Q is the set of states;
2. Σ is the input alphabet not containing the blank
symbol ⊔;
3. Γ is the tape alphabet, where ⊔ ∈ Γ and Σ ⊆ Γ;
4. δ : Q×Γ → Q×Γ×{L,R} is the transition
function;
5. q0 ∈ Q is the start state;
6. qaccept ∈ Q is the accept state;
7. qreject ∈ Q is the reject state.

**A configuration of the Turing machine consists of**

- the current state;
- the current tape contents;
- the current head location.

![](https://1.bp.blogspot.com/-VwHW07vA1TE/VUpOkqhKpZI/AAAAAAAApi4/3mJR_vK_buI/s400/擷取3.PNG)

Special configurations:
- start configuration: q0w;
- accepting configuration: the state is qaccept;
- rejecting configuration: the state is qreject;
- halting configuration: accepting and rejecting.

A Turing machine M accepts input w if a sequence of configurationsC1,C2,...,Ck exists,where

1. C1 is the start configuration of M on input w; 
2. Each Ci yields Ci+1;
3. Ck is an accepting configuration.

### Example:
A={0<sup>2<sup>n</sup></sup>|n≥0}
- Q={q1,q2,q3,q4,q5,qaccept,qreject},
- Σ={0},and
- Γ={0,x,␣}.
- We describe δ with a statediagram.
- Thestart,accept,and reject states are q<sub>1</sub>,q<sub>accept</sub>,and q<sub>reject</sub>,respectively.

![](https://1.bp.blogspot.com/-NlHza-ey1bE/VUpSed2UXlI/AAAAAAAApjY/9eyL8rQ6KYo/s640/擷取4.PNG)
