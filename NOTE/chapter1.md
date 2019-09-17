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
    
    **PRROF:** <br/>
    
    Let M<sub>1</sub> recognize A<sub>1</sub>, where M<sub>1</sub> = (Q<sub>1</sub>, Σ, δ<sub>1</sub>, q<sub>1</sub>, F<sub>1</sub>), <br/>
    and M<sub>2</sub> recognize A<sub>2</sub>, where M<sub>2</sub> = (Q<sub>2</sub>, Σ, δ<sub>2</sub>, q<sub>2</sub>, F<sub>2</sub>).<br/>
    Construct M to recognize A<sub>1</sub> ∪ A<sub>2</sub>, where M = (Q, Σ, δ, q<sub>0</sub>, F ).<br/>
    1. Q = {(r<sub>1</sub>, r<sub>2</sub>)| r<sub>1</sub> ∈ Q<sub>1</sub> and r<sub>2</sub> ∈ Q2}.
    2. Σ = Σ<sub>1</sub> ∪ Σ<sub>2</sub>.
    3. δ[(r<sub>1</sub>, r<sub>2</sub>), a] = [δ<sub>1</sub>(r<sub>1</sub>, a), δ<sub>2</sub>(r<sub>2</sub>, a)].
    4. q<sub>0</sub> is the pair (q<sub>1</sub>, q<sub>2</sub>).
    5. F ={(r<sub>1</sub>,r<sub>2</sub>)|r<sub>1</sub> ∈F<sub>1</sub> or r<sub>2</sub> ∈F<sub>2</sub>}.
    
- The class of regular languages is closed under the concatenation operation.

## 1.2 Nondeterminism

### Deterministic vs. nondeterministic

1. `Deterministic computation`: Determined next move.
2. `Nondeterministic computation`: Several choices may exist for the next move.

<br/>

- `NFA`: Nondeterministic finite automata
  > δ : Q × Σ<sub>ε → P(Q) is the transition function

![](https://1.bp.blogspot.com/-s3ECtmK1LK8/VT4NoPUazRI/AAAAAAAApG0/UgHWODQyRqQ/s1600/擷取.PNG)
<br/> 
<br/>
![](https://3.bp.blogspot.com/-G0C6SReom14/VT4OK1qS-tI/AAAAAAAApG8/HrCIkuG_pog/s1600/擷取2.PNG)