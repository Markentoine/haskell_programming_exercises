# Chapter One : All you need is lambda

## Intermission: Equivalence Exercises

1. `\xy.xz`
   b. `\mn.mz` is alpha equivalent to the lambda expression.
2. `\xy.xxy`
   c. `\a.(\b.aab)`
3. `\xyz.zx`
   b. `\tos.st`

## Chapter Exercises

### Combinators

1. `\x.xxx` is a combinator since there are no free variables. `x` binds all.
2. `\xy.zx` is not a combinator. `z` is a free variable.
3. `xyz.xy(xx)` is a combinator. `z` is in the head of the lambda.
4. `\xyz.xy(zxy)` is also a combinator since all the variables are bound.
5. `\xy.xy(zxy)` is not a combinator. `z` is free.

### Normal form or diverge

1. `𝜆𝑥.𝑥𝑥𝑥` is already at its normal form. Not possible to reduce it further.
2. `(𝜆𝑧.𝑧𝑧)(𝜆𝑦.𝑦𝑦)` is divergent: never ending loop of beta reductions.
3. `(𝜆𝑥.𝑥𝑥𝑥)𝑧` is convergent -> `zzz`

### Beta reduce

1. `(𝜆𝑎𝑏𝑐.𝑐𝑏𝑎)𝑧𝑧(𝜆𝑤𝑣.𝑤)` -> (\a.\b.\c.cba)(z)(z)(\w.\v.w) -> (\b.\c.cbz)(z)(\w.\v.w) -> (\c.czz)(\w.\v.w) -> (\w.\v.w)(z)z -> (\v.z)(z) -> z
2. `(𝜆𝑦.(𝜆𝑎.𝑎)𝑦𝑦)(𝑏)` -> (\a.a)bb -> bb
3. `(𝜆𝑦.𝑦)(𝜆𝑥.𝑥𝑥)(𝜆𝑧.𝑧𝑞)` -> (\x.xx)(\z.zq) -> (\z.zq)(\z.zq) -> (\z.zq)(q) -> qq
4. `(𝜆𝑧.𝑧)(𝜆𝑧.𝑧𝑧)(𝜆𝑧.𝑧𝑦)` -> (\z.zz)(\z.zy) -> (\z.zy)(\z.zy) -> (\z.zy)y -> yy
5. `(𝜆𝑥.𝜆𝑦.𝑥𝑦𝑦)(𝜆𝑦.𝑦)𝑦` -> (\y.y)(y)y -> yy
6. `(𝜆𝑎.𝑎𝑎)(𝜆𝑏.𝑏𝑎)𝑐` -> (\b.ba)(\b.ba)c -> (\b.ba)(a)c -> aac
7. `(𝜆𝑥𝑦𝑧.𝑥𝑧(𝑦𝑧))(𝜆𝑥.𝑧)(𝜆𝑥.𝑎)` -> (\x.\y.\w.xw(yw))(\a.z)(\b.c) [alpha equivalence] -> (<\y.\w.(\a.z1)w(yw)>)(\b.c) -> (\w.(\a.z1)w((\b.c)w)) -> \w.zc , a constant.
