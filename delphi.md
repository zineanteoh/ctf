# Blue Hens CTF 2022: Delphi

Sometimes knowing how to Google is important.

-   [Problem Description](#problem-description)
-   [A first look](#a-first-look)
-   [Reflection](#reflection)

## Problem Statement

See challenge here: https://ctftime.org/task/23808

```
CREATE OR REPLACE FUNCTION isPasswordCorrect wrapped
a000000
1
abcd
abcd
abcd
abcd
abcd
abcd
abcd
abcd
abcd
abcd
abcd
abcd
abcd
abcd
abcd
8
c8 f7
T/q+OkGAkyg+KSU59H5/cU61GPwwg1zwLZ4VfI7pkPiUcj5FRLJXjgd1G3kO2/EbeyIazcrn
jaJSL7VV403nKNFuahDqQu9uGatX1Isvhnl07QSEBEXZWT00onnKVUq6zFKYdRemK3sgquf1
E3mRJi4Jo6+woDkGme537Q4R1JSHhtPecFXe3RBwF5G0SyGAhCQQL7iNz4GdcvQDh/F6qJPE
m3IWQYW6WGZii5OXz5s2iX3ftg==

/
```

## A first look

The only thing provided to us in this challenge is the code above.

At first glance, it looked like some sort of SQL commands with some repeated 'abcd' that didn't seem to contain anything important.

A quick Google search confirms our hypothesis <i>(notice my search terms only contain important key words from the code)</i>:

![Google search](https://imgur.com/ODQRttC.png)

The first link tells us that the code above is a "wrapped PL/SQL source text." PL/SQL is a database programming language developed by [Oracle](https://www.oracle.com/database/technologies/appdev/plsql.html). Lucky for us, the Note section below says that "wrapping text does not prevent anyone from displaying it with a utility such as..."

![Oracle PL/SQL Page](https://imgur.com/phkiRq7.png)

Oh Cool! So we can click on that link and un-wrap the text using it!

Except, the link is broken.

So instead, I looked up how to unwrap PL/SQL code:

![Google search unwrap](https://imgur.com/kCPU91c.png)

And I immediately got a functioning tool:

![Unwrap PL/SQL](https://imgur.com/72pzFZd.png)

Which automatically unwrapped the obfuscated code to give us

![Flag](https://imgur.com/CSiuzZo.png)

And so the flag is found pretty effortlessly: `UDCTF{D0_No7_us3_0r4cle_Wr4p_4_P4ssw0rd!}`

## Reflection

This problem only has 13 solves out of 370+ teams.

I initially thought this was a difficult challenge. But thanks to this experience, I learned to not be discouraged by the low number of solves.

Sometimes all it takes is a few (clever) Google searches ;)
