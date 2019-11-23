# _Chapter 5 Reducibility_
- [_Chapter 5 Reducibility_](#_chapter-5-reducibility_)
  - [Undecidable Problems from Language Theory](#undecidable-problems-from-language-theory)

If problem A reduces to problem B, we can use a so- lution to B to solve A. Reducibility says NOTHING about solving A or B alone.

When A is reducible to B, solving A cannot be harder than solving B because a solution to B gives a solution to A. Therefore, if A is reducible to B,
- B is decidable ⇒ A is decidable;
- A is undecidable ⇒ B is undecidable.

## Undecidable Problems from Language Theory

```
HALTTM ={⟨M,w⟩ | M is a TM and M halts on input w}
```
HALT TM is undecidable.

![](https://i.imgur.com/raJ4DLr.png)

```
ETM ={⟨M⟩ | M is a TM and L(M)=∅}
```
ETM is undecidable.
![](https://i.imgur.com/cR4XiMY.png)

```
REGULARTM =
{⟨M⟩ | M is a TM and L(M) is a regular language}
```
REGULARTM is undecidable.
![](https://i.imgur.com/fyQKmsd.png)
```
EQTM ={⟨M1,M2⟩ | M1 and M2 are TMs and L(M1)=L(M2)}
```
E QTM is undecidable.
![](https://i.imgur.com/2kmSo1r.png)

```
ALBA ={⟨M,w⟩ | M is an LBA that accepts input string w}
```
ALBA ={⟨M,w⟩ | M is an LBA that accepts input string w}
![](https://i.imgur.com/031gTBV.png)

```
ELBA ={⟨M⟩ | M is an LBA where L(M)=∅}
```
ELBA is undecidable.
![](https://i.imgur.com/SkYMOoz.png)
![](https://i.imgur.com/xE936zo.png)

```
ALLCFG ={⟨G⟩ | G is a CFG and L(G)=Σ∗}
```
ALLCFG is undecidable.
![](https://i.imgur.com/ZojMRYq.png)
![](https://i.imgur.com/hZZB63c.png)
![](https://i.imgur.com/UJIyhmb.png)
![](https://i.imgur.com/SdXPOfy.png)

```
PCP = {⟨P⟩|P is a collection of dominoes with a match} is undecidable.
```

![](https://i.imgur.com/rHU5RUd.png)
![](https://i.imgur.com/o7ozOWg.png)
![](https://i.imgur.com/DtxN2bc.png)