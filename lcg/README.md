# lineer congruential generator

Sequence of random numbers

```math
X_{n+1} = (aX_n + c) \mod m
```

where:
- $X_0$, $X_1$, $X_2$,$...$ is the sequence of pseudorandom numbers,
- $X_i$  values is all integers,
- $a$, $c$, $m$ is all integers,
- $n$ is the index of the current number in the sequence,
- $a$ is the multiplier,
- $c$ is the increment,
- $m$ is the modulus,
- $X_0$ is the seed or initial value.


Assumption: $m > 0$ and $a < m, c < m, X_0 < m$


Example:
$a = 5$, $c = 1$, $m = 8$
and 
start seed is $ X_0 = 3$;
```math
X_1 = (5\cdot3 + 1)\mod 8 \\
X_1 = 16 \mod 8 \\
X_1 = 0
```

> $...$ In arithmetic,  $\textcolor{pink}{\colorbox{purple}{the remainder}}$ is the integer $\utilde{\text{"left over"}}$ after dividing one integer by another to produce an integer quotient (integer division). $\utilde{\text{The modulo operation}}$ is the operation that produces such a remainder when given a dividend and divisor
> *— [Wikipedia](https://en.wikipedia.org/wiki/Remainder)*


```math
X_2= (5\cdot0 + 1)\mod 8 \\
X_2 = 1 \mod 8 \\
X_2 = 1
```

```math
X_3= (5\cdot1 + 1)\mod 8 \\
X_3 = 6 \mod 8 \\
X_3 = 6
```
#
For $a = 5$, $c = 1$, $m = 8$ an $\textcolor{pink}{X_0 = 3}$;

| Step ($n$) | Formula Used                      | New Value $X_{n+1}$ |
|------------|-----------------------------------|---------------------|
| 0          | $X_1 = (5 \cdot 3 + 1) \mod 8$    | $X_1 = 0$           |
| 1          | $X_2 = (5 \cdot 0 + 1) \mod 8$    | $X_2 = 1$           |
| 2          | $X_3 = (5 \cdot 1 + 1) \mod 8$    | $X_3 = 6$           |
| 3          | $X_4 = (5 \cdot 6 + 1) \mod 8$    | $X_4 = 7$           |
| 4          | $X_5 = (5 \cdot 7 + 1) \mod 8$    | $X_5 = 4$           |
| 5          | $X_6 = (5 \cdot 4 + 1) \mod 8$    | $X_6 = 5$           |
| 6          | $X_7 = (5 \cdot 5 + 1) \mod 8$    | $X_7 = 2$           |
| 7          | $X_8 = (5 \cdot 2 + 1) \mod 8$    | $\textcolor{pink}{X_8 = 3}$|



#### we get a sequence m long
- the longest sequence you can get before it starts repeating is exactly $m$ numbers long.
- however, the actual period might be less than $m$.
    - This happens when the LCG does not use parameters that maximize the period.
    - For example, if the parameters are poorly chosen, the seuqence might start repeating after only a few numbers, which could be factor of $m$ (e.g., $\frac{m}{2}$, $\frac{m}{4}$, $..$)

#### the LCG produces a cyclic sequence

Limited range of values: Since the modulus $m$ restricts the values to a finite set of numbers (from $0$ to $m-1$), the sequence can only generate a limited number of unique numbers before it must repeat. This repetition is what forms a **cyclic sequence**.



#
The selection of the values for $a, c, m,$ and $X_0$ drastically affects the statistical properties and the cycle length.
choose m large and a,c so that sequence length is equal to $m$

If c = 0, the generator is often called a multiplicative congruential generator (MCG), or Lehmer RNG. If c ≠ 0, the method is called a mixed congruential generator.


Most digital computers use a binary representation of numbers
- Speed and efficiency are aided by a modulus, $m$, to be (or close to) a power of $2$.

# characteristic of a good generator 
The LCG has full period if and only if the following three conditions hold (Hull and Dobell, 1962): [^1]



1. The only positive integer that (exactly) divides both $m$ and $c$ is $1$
1. If $q$ is a prime number that divides $m$, then $q$ divides $a-1$
1. If $4$ divides $m$, then $4$ divides $a-1$

## References

1. [Prof. Dr. Mesut Güneş ▪ Ch. 6 Random-Number Generation](https://www.mi.fu-berlin.de/inf/groups/ag-tech/teaching/2012_SS/L_19540_Modeling_and_Performance_Analysis_with_Simulation/06.pdf)

1. [Hull and Dobell’s first theorem – Howard Rudd](https://www.howardrudd.net/mathematics/hull-and-dobells-first-theorem/)
1. [Linear congruential generator - Wikipedia](https://en.wikipedia.org/wiki/Linear_congruential_generator)
1. [Linear Congruential Random Number Generators](https://www.youtube.com/watch?v=BYR5sbJHqsU)
1. [Section II: Linear Congruential Generator I](https://pi.math.cornell.edu/~mec/Winter2009/Luo/Linear%20Congruential%20Generator/linear%20congruential%20gen1.html)
1. [Chapter 6 - Random-Number Generation](https://www.mi.fu-berlin.de/inf/groups/ag-tech/teaching/2012_SS/L_19540_Modeling_and_Performance_Analysis_with_Simulation/06.pdf)



https://www.youtube.com/watch?v=_tN2ev3hO14
https://www.youtube.com/watch?v=kRCmR4qr-hQ