
# _Chapter 1 Regular Language_

- [_Chapter 1 Regular Language_](#chapter-1-regular-language)
  - [1.1 FINITE AUTOMATA](#11-finite-automata)
    - [A finite automaton is a 5-tuple (Q, Σ, δ, q0, F ), where](#a-finite-automaton-is-a-5-tuple-q-%ce%a3-%ce%b4-q0-f--where)
    - [The Regular Operations](#the-regular-operations)
  - [1.2 Nondeterminism](#12-nondeterminism)
    - [Deterministic vs. nondeterministic](#deterministic-vs-nondeterministic)
    - [Equivalence of NFAs and DFAs](#equivalence-of-nfas-and-dfas)
    - [CLOSURE UNDER THE REGULAR OPERATIONS](#closure-under-the-regular-operations)
  - [1.3 Regular expression](#13-regular-expression)
    - [Definition:](#definition)
    - [Equivalence with Finite Automata](#equivalence-with-finite-automata)
  - [1.4 Pumping Lemma](#14-pumping-lemma)
  - [1.5 Closure Properties](#15-closure-properties)
  - [1.6 Myhill-Nerode Theorem](#16-myhill-nerode-theorem)
    - [Indistinguishable:](#indistinguishable)
    - [Myhill-Nerode theorem:](#myhill-nerode-theorem)
  - [1.7 Minimization of DFAs](#17-minimization-of-dfas)
    - [Table-filling Algorithm](#table-filling-algorithm)

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

### Equivalence of NFAs and DFAs
- Every NFA has an equivalent DFA.
  > Proof: 
  <br/>

  Let N = (Q, Σ, δ, q<sub>0</sub> , F ) be the NFA<br/>
  M =(Q′,Σ,δ′,q<sub>0</sub>′,F′) be the DFA
  1. Q′ = P(Q)
  2. R ∈ Q′ and a ∈ Σ, let δ′(R, a) = {q ∈ Q| q ∈ δ(r, a) for some r ∈ R}.
      >δ′(R, a) = U δ(r, a)
  3. q<sub>0</sub>′ = {q<sub>0</sub>}.
  4. F′ = {R ∈ Q′| R contains an accept state of N}.
    > The notation U δ(r, a) means: the union of the sets δ(r, a) for each possible r in R.

![](https://2.bp.blogspot.com/-XluxpL8zTew/VT4Y0amty8I/AAAAAAAApHQ/NJbSET8p8qY/s1600/擷取3.PNG)
![](https://4.bp.blogspot.com/-DqlPUgRoVsE/VT4Y0ddDwtI/AAAAAAAApHM/TyX-hG52AZk/s1600/擷取4.PNG)

### CLOSURE UNDER THE REGULAR OPERATIONS

![](https://1.bp.blogspot.com/-2cJQISrVCGM/VT4boVlbLnI/AAAAAAAApHo/eqoTV6-TU7g/s1600/Union.PNG)
![](https://1.bp.blogspot.com/-GiBouQ5amC4/VT4boeN16RI/AAAAAAAApHg/I3CrZy01b1I/s1600/concate.PNG)
![](https://4.bp.blogspot.com/-yyFnAJABuww/VT4boXaRKsI/AAAAAAAApHk/u131TMGTYU8/s1600/star.PNG)
  > add a accept state first because there are an empty language
- **use ε to creat a matched NFA**

## 1.3 Regular expression
### Definition:
```
1. a for some a in the alphabet Σ [L(a) = {a}];
2. ε [L(ε) = {ε}];
3. ∅ [L(∅) = ∅];
4. (R1 ∪ R2), where R1 and R2 are regular expressions [L(R1 ∪ R2) = L(R1) ∪ L(R2)];
5. (R1 ◦ R2), where R1 and R2 are regular expressions [L(R1 ◦ R2) = L(R1) ◦ L(R2)];
6. (R1∗), where R1 is a regular expression [L(R1∗) = (L(R1))∗].
```
![](https://1.bp.blogspot.com/-yojl8JiFh_E/VT4uH3gh47I/AAAAAAAApIM/yx-RLJhdKaw/s1600/擷取6.PNG)

### Equivalence with Finite Automata
  > Theorem : Every RE has an equivalent NFA

A GNFA accepts a string w in Σ∗ if w = w1w2 ···wk, where each wi ∈ Σ∗ and a sequenceof states q0, q1, · · · , qk exists such that
1. q0 = qstart; 
2. qk = qaccept;
3. for each i, we have wi ∈ L(Ri), where Ri = δ(qi−1, qi).
![](https://1.bp.blogspot.com/-w0qY8YS41uk/VT40AbTkAyI/AAAAAAAApIs/E_haffYvNeo/s1600/擷取.PNG)
![](https://3.bp.blogspot.com/-48or1jOqRWs/VT40XpqR6HI/AAAAAAAApI0/xg_k9u4fBz4/s1600/擷取3.PNG)


## 1.4 Pumping Lemma
 ### Pumping lemma: 
  ```
  If A is a regular language, then there is a number p (the pumping length) 
  where, if s is any string in A of length at least p, then s may be divided 
  into three pieces, s = xyz, satisfying the following conditions:
  ```
  1. for each i ≥ 0, xy<sup>i</sup>z ∈ A; 
  2. |y| > 0;
1. |xy| ≤ p.
  
  - nonregular language proof example:
  ![](https://2.bp.blogspot.com/-58o16BdMKnI/VT8ko5vpccI/AAAAAAAApcs/d9NkZOPMDv0/s1600/擷取2.PNG)

```
  How to use the pumping lemma:
1. Assume the language, say, B, is regular in order to obtain a contradiction.
2. By the pumping lemma, a pumping length p exists, and any string w ∈ B can be
     pumped if |w| ≥ p.
3. Find a string s ∈ B, |s| ≥ p, that s cannot be 
    pumped as described in the pumping lemma.
4. The contradiction is obtained, and therefore, B is
     proved to be nonregular.
```


## 1.5  Closure Properties

  ### Let A and B be regular languages. The results of the following operations are all regular languages:

- Union: A ∪ B;
- Concatenation: AB;
- Star: A∗;
- Intersection: A ∩ B;
- Complement: A (i.e., Σ∗ − A);
- Difference: A − B (A − B = A ∩ B); 
- Reversal: AR;
- Homomorphism: h(A);
- Inverse homomorphism: h−1(A).
> Homomorphism: A string substitution such that each symbol is replaced by a single string. That is,
> 
h:Σ→Π<sup>∗</sup>

```
For example, for an alphabet Σ = { a, b, c }, one possi-bility might be
Π = {0,1} 
h(a) = 11 
h(b) = 010 
h(c) = ε
abba → 1101001011 
abbcacc → 1101001011
```

>  Inverse homomorphism:<br/>
h−1(A⊆Π∗)={w | w∈Σ∗,h(w)∈A} .

## 1.6 Myhill-Nerode Theorem

### Indistinguishable:

Let x and y be strings and L be any language.
We say that x and y are **distinguishable** by L if some string z exists whereby exactly 
one of the strings xz and yz is a member of L;
otherwise, for every string z, we have xz ∈ L whenever yz ∈ L and we say that x 
and y are **indistinguishable** by L.


- If x and y are indistinguishable by L we write x ≡<sub>L</sub> y.
  > In other words, for x,y ∈ Σ∗,<br>
  x≡<sub>L</sub> y iff foreach z∈Σ∗ : xz∈L ⇔ yz∈L.

- ≡<sub>L</sub> is an equivlance relation because obviously
  1. Reflexive: x ≡<sub>L</sub> x;
  2. Symmetric: x ≡<sub>L</sub> y ⇒ y ≡<sub>L</sub> x;
  3. Transitive: x ≡<sub>L</sub> y ∧ y ≡L z ⇒ x ≡<sub>L</sub> z.
  
- For example, Σ = {0,1}. Let L<sub>0</sub> = {0<sup>n</sup> | n>0}, and define ≡L<sub>0</sub> by using L<sub>0</sub>. We have
  -  0 ≡L<sub>0</sub> 000 
  -  11 ≡L<sub>0</sub> 101 
  -  ε ~~\≡~~L<sub>0</sub> 00

### Myhill-Nerode theorem:
```
Let L be a language and let X be a set of strings. 
Say that X is pairwise dis-tinguishable by L if every
two distinct strings in X are distinguishable by L.
```
  > **Index of L:**<br/>
  maximum number of elements in any set that is pair- wise distinguishable by L.
1. If L is recognized by a DFA with k states, L has index at most k.
2. If the index of L is a finite number k, it is recognized by a DFA with k states.
3. L is regular iff it has finite index. Moreover, its index is the size of the smallest DFA recognizing it.
- **How to use Myhill-Nerode theorem:**
  1. Given a langauge B, construct the equivalence rela- tion ≡B by using B.
  2. Prove that B has finite or infinite index: 
     -  Finite: B is a regular language.
     - Infinite: B is not a regular language.
> Myhill-Nerode theorem is better than pumping lemma to prove a language is regular

## 1.7 Minimization of DFAs
- **Equivalent states:**
  > State p and state q are said to be equivalent if for all w ∈ Σ∗, δˆ(p,w) ∈ F ⇔ δˆ(q,w) ∈ F; and distinguishable otherwise.

### Table-filling Algorithm
**DFA A = (Q, Σ, δ, q0, F )**

- **Basis:** If p∈F and q/∈F,{p,q} is distinguishable.
- **Induction step:** If { r, s } is distinguishable, and<br/>
  r = δ(p, a) <br/> s = δ(q, a) <br/>
  for some a ∈ Σ, then { p, q } is distinguishable.
**Examples:**
![](https://3.bp.blogspot.com/-a6d9maAf3yc/VT_CEpa-eAI/AAAAAAAApdE/bxlmfJBky4g/s1600/擷取.PNG)
![](https://1.bp.blogspot.com/-ZXfv-ANrGGs/VT_GQl90-CI/AAAAAAAApdQ/Ro86aP8VfcI/s1600/擷取2.PNG)

<!-- page 17 -->