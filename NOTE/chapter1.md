# *__Chapter1 <br/> Regular Language__*

## 1.1 FINITE AUTOMATA

### A finite automaton is a 5-tuple (Q, Σ, δ, q0, F ), where

1. Q is a finite set called the `states`;
2. Σ is a finite set called the `alphabet`;
3. δ : Q × Σ → Q is the `transition function`;
4. q0 ∈ Q: is the `start state`;
5. F ⊆ Q is the set of `accept states` or final states.
    >- with double circle

![](https://2.bp.blogspot.com/-1TwikhINV1U/VPfNsrmqIHI/AAAAAAAAmok/UAqtXoLJXFA/s1600/螢幕快照%2B2015-03-05%2B上午11.04.12.png)

- when we feed the input string 1101 into the machin
<br/>
  1. Start in state q1.
  2. Read 1, follow transition from q1 to q2.
  3. Read 1, follow transition from q2 to q2.
  4. Read 0, follow transition from q2 to q3.
  5. Read 1, follow transition from q3 to q2.
  6. Accept because M1 is `in an accept state q2 at the end of the input`.
   
- If A is the set of all strings that machine M accepts, we
say that A is the language of machine M and write

    **`L(M) = A`** 

- We say that `M recognizes A` or `M accepts A`. A ma- chine always recognizes `only one language`.
  
- If the machine accepts no strings, it still recognizes one language— namely, the `empty language ∅`.

- `A language is called a regular language if some finite automaton recognizes it.`
### The Regular Operations

1. **Union:** <br/>
A ∪ B = {x | x ∈ A or x ∈ B};
2. **Concatenation:**<br/>
A ◦ B = {xy | x ∈ A and y ∈ B};
3. **Star:**<br/>
  A<sup>∗</sup> ={x<sub>1</sub>x<sub>2</sub>···x<sub>k</sub> | k≥0 and each x<sub>i</sub> ∈A}.<br/>
    > =A<sup>0</sup> ∪ A<sup>1</sup> ∪ A<sup>2</sup> ∪ A<sup>3</sup> ...
        
- The class of regular languages is closed under the union operation.<br/>
    >**PRROF:** <br/>
    ```
    Let M1 recognize A1, where M1 = (Q1, Σ, δ1, q1, F1), 
    and M2 recognize A2, where M2 = (Q2, Σ, δ2, q2, F2).
    Construct M to recognize A1 ∪ A2, where M = (Q, Σ, δ, q0, F ).
        1.Q = {(r1, r2)| r1 ∈ Q1 and r2 ∈ Q2}.
        2.Σ = Σ1 ∪ Σ2.
        3.δ[(r1, r2), a] = [δ1(r1, a), δ2(r2, a)].
        4.q0 is the pair (q1, q2).
        5.F ={(r1,r2)|r1 ∈F1 orr2 ∈F2}.
    ```
- The class of regular languages is closed under the concatenation operation.
