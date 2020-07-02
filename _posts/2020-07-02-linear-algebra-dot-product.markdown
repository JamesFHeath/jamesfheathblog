---
layout: post
title:  "Linear Algebra: Dot Product, Vector Length, Angles Between Vectors"
categories: math
tags: linearalgebra math vectors
---

<body 
>
   <h3 class="likesectionHead"><a 
 id="x1-1000"></a>Linear Algebra: Vector Dot Product</h3>
<!--l. 13--><p class="noindent" >The dot product operation is a way to multiply a vector by
another vector. Dot product notation is, not surprisingly, just a
<!--l. 14--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mo 
class="MathClass-bin">&#x22C5;</mo></math> between two
vectors: <!--l. 14--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></math>.
(<!--l. 15--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mo 
class="MathClass-bin">&#x00D7;</mo></math> between
vectors is the cross product, a different vector multiplication). The dot product is defined
as <!--l. 16--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><msub><mrow 
><mi 
>a</mi></mrow><mrow 
><mn>1</mn></mrow></msub 
><mo 
class="MathClass-punc">,</mo><msub><mrow 
><mi 
>a</mi></mrow><mrow 
><mn>2</mn></mrow></msub 
><mo 
class="MathClass-punc">,</mo><mi 
class="MathClass-op">&#x2026;</mi><mo> &ApplyFunction;<!--FUNCTION APPLICATION--></mo><mo 
class="MathClass-punc">,</mo><msub><mrow 
><mi 
>a</mi></mrow><mrow 
><mi 
>n</mi></mrow></msub 
></mrow><mo 
class="MathClass-close">)</mo></mrow> <mo 
class="MathClass-bin">&#x22C5;</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><msub><mrow 
><mi 
>b</mi></mrow><mrow 
><mn>1</mn></mrow></msub 
><mo 
class="MathClass-punc">,</mo><msub><mrow 
><mi 
>b</mi></mrow><mrow 
><mn>2</mn></mrow></msub 
><mo 
class="MathClass-punc">,</mo><mi 
class="MathClass-op">&#x2026;</mi><mo> &ApplyFunction;<!--FUNCTION APPLICATION--></mo><mo 
class="MathClass-punc">,</mo><msub><mrow 
><mi 
>b</mi></mrow><mrow 
><mi 
>n</mi></mrow></msub 
></mrow><mo 
class="MathClass-close">)</mo></mrow> <mo 
class="MathClass-rel">=</mo> <msub><mrow 
><mi 
>a</mi></mrow><mrow 
><mn>1</mn></mrow></msub 
> <mo 
class="MathClass-bin">&#x2217;</mo> <msub><mrow 
><mi 
>b</mi></mrow><mrow 
><mn>1</mn></mrow></msub 
> <mo 
class="MathClass-bin">+</mo> <msub><mrow 
><mi 
>a</mi></mrow><mrow 
><mn>2</mn></mrow></msub 
> <mo 
class="MathClass-bin">&#x2217;</mo> <msub><mrow 
><mi 
>b</mi></mrow><mrow 
><mn>2</mn></mrow></msub 
> <mo 
class="MathClass-bin">+</mo> <mo 
class="MathClass-rel">&#x22EF;</mo> <mo 
class="MathClass-bin">+</mo> <msub><mrow 
><mi 
>a</mi></mrow><mrow 
><mi 
>n</mi></mrow></msub 
> <mo 
class="MathClass-bin">&#x2217;</mo> <msub><mrow 
><mi 
>b</mi></mrow><mrow 
><mi 
>n</mi></mrow></msub 
></math>.
The dot product takes two vectors, and generates just a number. For example,
<!--l. 18--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mrow ><mo 
class="MathClass-open">(</mo><mrow><mn>1</mn><mo 
class="MathClass-punc">,</mo><mn>3</mn></mrow><mo 
class="MathClass-close">)</mo></mrow> <mo 
class="MathClass-bin">&#x22C5;</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mn>4</mn><mo 
class="MathClass-punc">,</mo><mn>7</mn></mrow><mo 
class="MathClass-close">)</mo></mrow> <mo 
class="MathClass-rel">=</mo> <mn>1</mn> <mo 
class="MathClass-bin">&#x2217;</mo> <mn>4</mn> <mo 
class="MathClass-bin">+</mo> <mn>3</mn> <mo 
class="MathClass-bin">&#x2217;</mo> <mn>7</mn> <mo 
class="MathClass-rel">=</mo> <mn>4</mn> <mo 
class="MathClass-bin">+</mo> <mn>2</mn><mn>1</mn> <mo 
class="MathClass-rel">=</mo> <mn>2</mn><mn>5</mn></math>.
</p><!--l. 20--><p class="noindent" >
</p>
   <h3 class="likesectionHead"><a 
 id="x1-2000"></a>Dot Product Relation to Vector Length</h3>
<!--l. 21--><p class="noindent" >To find the length of a vector in 2 dimensions, we just need to take the square root of
its components squared. This is just the Pythagorean theorem. For example,
<!--l. 23--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mn>3</mn><mo 
class="MathClass-punc">,</mo><mn>4</mn></mrow><mo 
class="MathClass-close">)</mo></mrow></math>, then its length denoted
with double lines is <!--l. 23--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo> <mo 
class="MathClass-rel">=</mo> <msqrt><mrow><msup><mrow 
><mn>3</mn></mrow><mrow 
><mn>2</mn> </mrow> </msup 
> <mo 
class="MathClass-bin">+</mo> <msup><mrow 
><mn>4</mn></mrow><mrow 
><mn>2</mn></mrow></msup 
></mrow></msqrt> <mo 
class="MathClass-rel">=</mo> <msqrt><mrow><mn>9</mn> <mo 
class="MathClass-bin">+</mo> <mn>1</mn><mn>6</mn></mrow></msqrt> <mo 
class="MathClass-rel">=</mo> <msqrt><mrow><mn>2</mn><mn>5</mn></mrow></msqrt> <mo 
class="MathClass-rel">=</mo> <mn>5</mn></math>.
We can generalize this notion of length to any number of dimensions by adding
additional vector terms to the sum under the sqrt. Generalized Pythagorean theorem:
<!--l. 25--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>v</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo> <mo 
class="MathClass-rel">=</mo> <msqrt><mrow><msubsup><mrow 
><mi 
>v</mi></mrow><mrow 
><mn>1</mn> </mrow> <mrow 
>  <mn>2</mn> </mrow> </msubsup 
> <mo 
class="MathClass-bin">+</mo> <msubsup><mrow 
><mi 
>v</mi></mrow><mrow 
><mn>2</mn> </mrow> <mrow 
>  <mn>2</mn> </mrow> </msubsup 
> <mo 
class="MathClass-bin">+</mo> <mo 
class="MathClass-rel">&#x22EF;</mo> <mo 
class="MathClass-bin">+</mo> <msubsup><mrow 
><mi 
>v</mi></mrow><mrow 
><mi 
>n</mi> </mrow> <mrow 
>  <mn>2</mn></mrow></msubsup 
></mrow></msqrt></math>.
Notice that a vector &#x201D;dotted&#x201D; with itself, will get all the terms of
the vector squared. So, to get the length using the dot product, we
just need to take the square root of the vector &#x201D;dotted&#x201D; with itself.
<!--l. 28--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>v</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo> <mo 
class="MathClass-rel">=</mo> <msqrt><mrow><mover 
accent="true"><mrow 
><mi 
>v</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo> <mover 
accent="true"><mrow 
><mi 
>v</mi></mrow><mo accent="true">&#x2192;</mo></mover></mrow></msqrt></math>.
</p><!--l. 31--><p class="noindent" >
</p>
   <h3 class="likesectionHead"><a 
 id="x1-3000"></a>Cauchy-Schwarz Inequality</h3>
<!--l. 32--><p class="noindent" >The Cauchy-Schwarz Inequality relates vector dot products to vector magnitudes,
and generalizes to any number of dimensions. The inequality states that the absolute
values of the dot product of two vectors is less than the value of their lengths multiplied:
<!--l. 33--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">&#x2264;</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-bin">&#x2217;</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo></math> where
<!--l. 33--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-punc">,</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">&#x2208;</mo> <msup><mrow 
><mi 
>&#x211D;</mi></mrow><mrow 
><mi 
>n</mi></mrow></msup 
> <mo 
class="MathClass-bin">&#x2227;</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-punc">,</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">&#x2260;</mo><mover 
accent="true"><mrow 
><mn>0</mn></mrow><mo accent="true">&#x2192;</mo></mover></math>.
The two vectors are only equal when they are colinear:
<!--l. 34--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo> <mo 
class="MathClass-rel">=</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x2217;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mspace width="0.28em" class="thickpace"/><mo 
class="MathClass-rel">&#x21D4;</mo><mspace width="0.28em" class="thickpace"/><mi 
class="MathClass-op">&#x2203;</mi><mo> &ApplyFunction;<!--FUNCTION APPLICATION--></mo><mrow ><mo 
class="MathClass-open">(</mo><mrow><mi 
>c</mi> <mo 
class="MathClass-rel">&#x2208;</mo> <mi 
>&#x211D;</mi></mrow><mo 
class="MathClass-close">)</mo></mrow><!--mstyle 
class="text"--><mtext  >&#x00A0;&#x00A0;for&#x00A0;</mtext><!--/mstyle--><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mi 
>c</mi> <mo 
class="MathClass-bin">&#x2217;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></math>.
</p><table class="equation-star"><tr><td>

<!--l. 35--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
     <mi 
>p</mi><mrow ><mo 
class="MathClass-open">(</mo><mrow><mi 
>t</mi></mrow><mo 
class="MathClass-close">)</mo></mrow> <mo 
class="MathClass-rel">=</mo> <mover 
accent="true"><mrow 
><mi 
>v</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>t</mi><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x2212;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-rel">&#x2265;</mo> <mn>0</mn><!--mstyle 
class="text"--><mtext  >&#x00A0;&#x00A0;because&#x00A0;</mtext><!--/mstyle--><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>v</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo> <mo 
class="MathClass-rel">=</mo> <msqrt><mrow><mi 
>c</mi><mi 
>o</mi><mi 
>m</mi><mi 
>p</mi><mi 
>o</mi><mi 
>n</mi><mi 
>e</mi><mi 
>n</mi><mi 
>t</mi><mi 
>s</mi> <mo 
class="MathClass-rel">&#x003E;</mo><mo 
class="MathClass-rel">=</mo> <mn>0</mn></mrow></msqrt>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 36--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                          <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>v</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-rel">=</mo> <mover 
accent="true"><mrow 
><mi 
>v</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo><mover 
accent="true"><mrow 
><mi 
>v</mi></mrow><mo accent="true">&#x2192;</mo></mover>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 37--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                        <mrow ><mo 
class="MathClass-open">(</mo><mrow><mi 
>t</mi><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x2212;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></mrow><mo 
class="MathClass-close">)</mo></mrow> <mo 
class="MathClass-bin">&#x22C5;</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mi 
>t</mi><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x2212;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></mrow><mo 
class="MathClass-close">)</mo></mrow>
</math></td></tr></table>
   <table class="equation-star"><tr><td>

<!--l. 38--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
        <!--mstyle 
class="text"--><mtext  >&#x00A0;Dot&#x00A0;product&#x00A0;is&#x00A0;distributive,&#x00A0;communative,&#x00A0;and&#x00A0;associative</mtext><!--/mstyle-->
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 39--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                <mi 
>t</mi><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo> <mi 
>t</mi><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x2212;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo> <mi 
>t</mi><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x2212;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo> <mi 
>t</mi><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">+</mo> <mo 
class="MathClass-bin">&#x2212;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo><mo 
class="MathClass-bin">&#x2212;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 40--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                  <mrow ><mo 
class="MathClass-open">(</mo><mrow><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover></mrow><mo 
class="MathClass-close">)</mo></mrow><msup><mrow 
><mi 
>t</mi></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-bin">&#x2212;</mo> <mn>2</mn><mrow ><mo 
class="MathClass-open">(</mo><mrow><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></mrow><mo 
class="MathClass-close">)</mo></mrow><mi 
>t</mi> <mo 
class="MathClass-bin">+</mo> <mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">&#x2265;</mo> <mn>0</mn>
</math></td></tr></table>
   <table class="equation-star"><tr><td>

<!--l. 41--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                 <mi 
>x</mi> <mo 
class="MathClass-rel">=</mo> <mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-punc">,</mo><mi 
>y</mi> <mo 
class="MathClass-rel">=</mo> <mn>2</mn><mrow ><mo 
class="MathClass-open">(</mo><mrow><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></mrow><mo 
class="MathClass-close">)</mo></mrow><mo 
class="MathClass-punc">,</mo><mi 
>z</mi> <mo 
class="MathClass-rel">=</mo> <mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 42--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                       <mi 
>p</mi><mrow ><mo 
class="MathClass-open">(</mo><mrow><mi 
>t</mi></mrow><mo 
class="MathClass-close">)</mo></mrow> <mo 
class="MathClass-rel">=</mo> <mi 
>x</mi><msup><mrow 
><mi 
>t</mi></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-bin">&#x2212;</mo> <mi 
>y</mi><mi 
>t</mi> <mo 
class="MathClass-bin">+</mo> <mi 
>z</mi> <mo 
class="MathClass-rel">&#x2265;</mo> <mn>0</mn>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 43--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                     <mi 
>p</mi><mrow ><mo 
class="MathClass-open">(</mo><mrow> <mfrac><mrow 
><mi 
>y</mi></mrow>
<mrow 
><mn>2</mn><mi 
>x</mi></mrow></mfrac></mrow><mo 
class="MathClass-close">)</mo></mrow> <mo 
class="MathClass-rel">=</mo> <mi 
>x</mi> <mfrac><mrow 
><msup><mrow 
><mi 
>y</mi></mrow><mrow 
><mn>2</mn></mrow></msup 
></mrow>
<mrow 
><mn>4</mn><msup><mrow 
><mi 
>x</mi></mrow><mrow 
><mn>2</mn></mrow></msup 
></mrow></mfrac> <mo 
class="MathClass-bin">&#x2212;</mo> <mfrac><mrow 
><msup><mrow 
><mi 
>y</mi></mrow><mrow 
><mn>2</mn></mrow></msup 
></mrow> 
<mrow 
><mn>2</mn><mi 
>x</mi></mrow></mfrac> <mo 
class="MathClass-bin">+</mo> <mi 
>z</mi> <mo 
class="MathClass-rel">&#x2265;</mo> <mn>0</mn>
</math></td></tr></table>
   <table class="equation-star"><tr><td>

<!--l. 44--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                          <mfrac><mrow 
><msup><mrow 
><mi 
>y</mi></mrow><mrow 
><mn>2</mn></mrow></msup 
></mrow>
<mrow 
><mn>4</mn><mi 
>x</mi></mrow></mfrac> <mo 
class="MathClass-bin">&#x2212;</mo> <mfrac><mrow 
><msup><mrow 
><mi 
>y</mi></mrow><mrow 
><mn>2</mn></mrow></msup 
></mrow> 
<mrow 
><mn>2</mn><mi 
>x</mi></mrow></mfrac> <mo 
class="MathClass-bin">+</mo> <mi 
>z</mi> <mo 
class="MathClass-rel">&#x2265;</mo> <mn>0</mn>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 45--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                          <mfrac><mrow 
><msup><mrow 
><mi 
>y</mi></mrow><mrow 
><mn>2</mn></mrow></msup 
></mrow>
<mrow 
><mn>4</mn><mi 
>x</mi></mrow></mfrac> <mo 
class="MathClass-bin">&#x2212;</mo><mfrac><mrow 
><mn>2</mn><msup><mrow 
><mi 
>y</mi></mrow><mrow 
><mn>2</mn></mrow></msup 
></mrow> 
 <mrow 
><mn>4</mn><mi 
>x</mi></mrow></mfrac> <mo 
class="MathClass-bin">+</mo> <mi 
>z</mi> <mo 
class="MathClass-rel">&#x2265;</mo> <mn>0</mn>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 46--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                           <mo 
class="MathClass-bin">&#x2212;</mo><mfrac><mrow 
><msup><mrow 
><mi 
>y</mi></mrow><mrow 
><mn>2</mn></mrow></msup 
></mrow>
<mrow 
><mn>4</mn><mi 
>x</mi></mrow></mfrac> <mo 
class="MathClass-bin">+</mo> <mi 
>z</mi> <mo 
class="MathClass-rel">&#x2265;</mo> <mn>0</mn>
</math></td></tr></table>
   <table class="equation-star"><tr><td>

<!--l. 47--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                              <mi 
>z</mi> <mo 
class="MathClass-rel">&#x2265;</mo> <mfrac><mrow 
><msup><mrow 
><mi 
>y</mi></mrow><mrow 
><mn>2</mn></mrow></msup 
></mrow> 
<mrow 
><mn>4</mn><mi 
>x</mi></mrow></mfrac>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 48--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                             <mn>4</mn><mi 
>x</mi><mi 
>z</mi> <mo 
class="MathClass-rel">&#x2265;</mo> <msup><mrow 
><mi 
>y</mi></mrow><mrow 
><mn>2</mn></mrow></msup 
>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 49--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                   <mn>4</mn><mrow ><mo 
class="MathClass-open">(</mo><mrow><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></mrow><mo 
class="MathClass-close">)</mo></mrow> <mo 
class="MathClass-rel">&#x2265;</mo> <msup><mrow 
><mrow ><mo 
class="MathClass-open">(</mo><mrow><mn>2</mn><mrow ><mo 
class="MathClass-open">(</mo><mrow><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></mrow><mo 
class="MathClass-close">)</mo></mrow></mrow><mo 
class="MathClass-close">)</mo></mrow></mrow><mrow 
><mn>2</mn></mrow></msup 
>
</math></td></tr></table>
   <table class="equation-star"><tr><td>

<!--l. 50--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                    <mn>4</mn><mrow ><mo 
class="MathClass-open">(</mo><mrow><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-bin">&#x2217;</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
></mrow><mo 
class="MathClass-close">)</mo></mrow> <mo 
class="MathClass-rel">&#x2265;</mo> <mn>4</mn><msup><mrow 
><mrow ><mo 
class="MathClass-open">(</mo><mrow><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></mrow><mo 
class="MathClass-close">)</mo></mrow></mrow><mrow 
><mn>2</mn></mrow></msup 
>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 51--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                      <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-bin">&#x2217;</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-rel">&#x2265;</mo> <msup><mrow 
><mrow ><mo 
class="MathClass-open">(</mo><mrow><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></mrow><mo 
class="MathClass-close">)</mo></mrow></mrow><mrow 
><mn>2</mn></mrow></msup 
>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 52--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                       <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-bin">&#x2217;</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">&#x2265;</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo>
</math></td></tr></table>

<!--l. 54--><p class="noindent" >
</p>
   <h3 class="likesectionHead"><a 
 id="x1-4000"></a>Triangle Inequality</h3>
<!--l. 55--><p class="noindent" >We can use the Cauchy-Schwarz Inequality to define a triangle inequality using any 2
vectors in any number of dimensions. The Triangle Inequality states that the sum of
two sides of a triangle must be greater than or equal to the length of the third side.
<!--l. 57--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mi 
>z</mi> <mo 
class="MathClass-rel">&#x2264;</mo> <mi 
>x</mi> <mo 
class="MathClass-bin">+</mo> <mi 
>y</mi></math>, only
equal when talking about a line. We can expand this definition to vectors with
<!--l. 58--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>x</mi> <mo 
class="MathClass-bin">+</mo> <mi 
>y</mi><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">&#x2264;</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>x</mi><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo> <mo 
class="MathClass-bin">+</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>y</mi><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo></math>,
where they are only equal when the vectors are colinear. </p><table class="equation-star"><tr><td>
<!--l. 59--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                     <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>x</mi> <mo 
class="MathClass-bin">+</mo> <mi 
>y</mi><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mi 
>x</mi> <mo 
class="MathClass-bin">+</mo> <mi 
>y</mi></mrow><mo 
class="MathClass-close">)</mo></mrow> <mo 
class="MathClass-bin">&#x22C5;</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mi 
>x</mi> <mo 
class="MathClass-bin">+</mo> <mi 
>y</mi></mrow><mo 
class="MathClass-close">)</mo></mrow>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 60--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
               <mrow ><mo 
class="MathClass-open">(</mo><mrow><mi 
>x</mi> <mo 
class="MathClass-bin">+</mo> <mi 
>y</mi></mrow><mo 
class="MathClass-close">)</mo></mrow> <mo 
class="MathClass-bin">&#x22C5;</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mi 
>x</mi> <mo 
class="MathClass-bin">+</mo> <mi 
>y</mi></mrow><mo 
class="MathClass-close">)</mo></mrow> <mo 
class="MathClass-rel">=</mo> <mi 
>x</mi> <mo 
class="MathClass-bin">&#x22C5;</mo> <mi 
>x</mi> <mo 
class="MathClass-bin">+</mo> <mi 
>x</mi> <mo 
class="MathClass-bin">&#x22C5;</mo> <mi 
>y</mi> <mo 
class="MathClass-bin">+</mo> <mi 
>x</mi> <mo 
class="MathClass-bin">&#x22C5;</mo> <mi 
>y</mi> <mo 
class="MathClass-bin">+</mo> <mi 
>y</mi> <mo 
class="MathClass-bin">&#x22C5;</mo> <mi 
>y</mi>
</math></td></tr></table>
   <table class="equation-star"><tr><td>

<!--l. 61--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                        <!--mstyle 
class="text"--><mtext  >&#x00A0;Recall:&#x00A0;</mtext><!--/mstyle--><mi 
>x</mi> <mo 
class="MathClass-bin">&#x22C5;</mo> <mi 
>x</mi> <mo 
class="MathClass-rel">=</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>x</mi><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 62--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                    <!--mstyle 
class="text"--><mtext  >&#x00A0;Becomes:&#x00A0;</mtext><!--/mstyle--><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>x</mi><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-bin">+</mo> <mn>2</mn><mi 
>x</mi> <mo 
class="MathClass-bin">&#x22C5;</mo> <mi 
>y</mi> <mo 
class="MathClass-bin">+</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>y</mi><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 63--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
         <!--mstyle 
class="text"--><mtext  >&#x00A0;We&#x00A0;know&#x00A0;from&#x00A0;Cauchy-Schwarz:&#x00A0;</mtext><!--/mstyle--><mi 
>x</mi> <mo 
class="MathClass-bin">&#x22C5;</mo> <mi 
>y</mi> <mo 
class="MathClass-rel">&#x2264;</mo><mo 
class="MathClass-rel">|</mo><mi 
>x</mi> <mo 
class="MathClass-bin">&#x22C5;</mo> <mi 
>y</mi><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">&#x2264;</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>x</mi><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>y</mi><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo>
</math></td></tr></table>
   <table class="equation-star"><tr><td>

<!--l. 64--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
             <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>x</mi><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-bin">+</mo> <mn>2</mn><mi 
>x</mi> <mo 
class="MathClass-bin">&#x22C5;</mo> <mi 
>y</mi> <mo 
class="MathClass-bin">+</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>y</mi><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-rel">&#x2264;</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>x</mi><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-bin">+</mo> <mn>2</mn><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>x</mi><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>y</mi><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo> <mo 
class="MathClass-bin">+</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>y</mi><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 65--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                  <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>x</mi> <mo 
class="MathClass-bin">+</mo> <mi 
>y</mi><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-rel">&#x2264;</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>x</mi><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-bin">+</mo> <mn>2</mn><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>x</mi><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>y</mi><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo> <mo 
class="MathClass-bin">+</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>y</mi><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 66--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                      <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>x</mi> <mo 
class="MathClass-bin">+</mo> <mi 
>y</mi><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-rel">&#x2264;</mo> <msup><mrow 
><mrow ><mo 
class="MathClass-open">(</mo><mrow><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>x</mi><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo> <mo 
class="MathClass-bin">+</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>y</mi><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo></mrow><mo 
class="MathClass-close">)</mo></mrow></mrow><mrow 
><mn>2</mn></mrow></msup 
>
</math></td></tr></table>
   <table class="equation-star"><tr><td>

<!--l. 67--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                        <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>x</mi> <mo 
class="MathClass-bin">+</mo> <mi 
>y</mi><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">&#x2264;</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>x</mi><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo> <mo 
class="MathClass-bin">+</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>y</mi><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo>
</math></td></tr></table>
<!--l. 68--><p class="indent" >   Visually, if we take (1,3) and (3,4) we can create a triangle from their
sum.
<div style="text-align: center"><img src="/images/vector_triangle_3.png" alt="Vector Triangle"/></div>
</p><!--l. 70--><p class="indent" >   Or a line if the two vectors are colinear (drawn parallel to show better).
<div style="text-align: center"><img src="/images/vector_triangle_2.png" alt="Parallel Vectors"/></div>
</p><!--l. 73--><p class="noindent" >
</p>
   <h3 class="likesectionHead"><a 
 id="x1-5000"></a>Angle Between Vectors, Perpendicularity, Orthogonality</h3>
<!--l. 74--><p class="noindent" >We&#x2019;ve defined the triangle inequality in any number of dimensions, and the payoff is that we
can then define angles between vectors in any number of dimsensions. Let&#x2019;s define a triangle
with lengths <!--l. 75--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-punc">,</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-punc">,</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x2212;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo></math>
and see if we can define angles between vectors using the triangle inequality and Law of
Cosines <!--l. 75--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><msup><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-rel">=</mo> <msup><mrow 
><mi 
>a</mi></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-bin">+</mo> <msup><mrow 
><mi 
>b</mi></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-bin">&#x2212;</mo> <mn>2</mn><mi 
>a</mi><mi 
>b</mi><mi class="qopname">cos</mi><mo> &ApplyFunction;<!--FUNCTION APPLICATION--> </mo><!--nolimits--><mrow ><mo 
class="MathClass-open">(</mo><mrow><mi 
>&#x1D703;</mi></mrow><mo 
class="MathClass-close">)</mo></mrow></math>.
</p><table class="equation-star"><tr><td>
<!--l. 76--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
            <!--mstyle 
class="text"--><mtext  >&#x00A0;Recall&#x00A0;Triangle&#x00A0;Inequality:&#x00A0;</mtext><!--/mstyle--><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>x</mi> <mo 
class="MathClass-bin">+</mo> <mi 
>y</mi><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">&#x2264;</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>x</mi><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo> <mo 
class="MathClass-bin">+</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>y</mi><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo>
</math></td></tr></table>
   <table class="equation-star"><tr><td>

<!--l. 77--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
             <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo> <mo 
class="MathClass-rel">=</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">+</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x2212;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></mrow><mo 
class="MathClass-close">)</mo></mrow> <mo 
class="MathClass-rel">&#x003C;</mo><mo 
class="MathClass-rel">=</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>v</mi><mi 
>e</mi><mi 
>c</mi><mi 
>b</mi><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo> <mo 
class="MathClass-bin">+</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x2212;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 78--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
             <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo> <mo 
class="MathClass-rel">=</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">+</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x2212;</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover></mrow><mo 
class="MathClass-close">)</mo></mrow> <mo 
class="MathClass-rel">&#x003C;</mo><mo 
class="MathClass-rel">=</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>v</mi><mi 
>e</mi><mi 
>c</mi><mi 
>a</mi><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo> <mo 
class="MathClass-bin">+</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x2212;</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 79--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                 <!--mstyle 
class="text"--><mtext  >&#x00A0;Sidebar:&#x00A0;</mtext><!--/mstyle--><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x2212;</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo> <mo 
class="MathClass-rel">=</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-bin">&#x2212;</mo> <mn>1</mn><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x2212;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo>
</math></td></tr></table>
   <table class="equation-star"><tr><td>

<!--l. 80--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
        <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x2212;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo> <mo 
class="MathClass-rel">=</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">+</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mo 
class="MathClass-bin">&#x2212;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></mrow><mo 
class="MathClass-close">)</mo></mrow><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo> <mo 
class="MathClass-rel">&#x003C;</mo><mo 
class="MathClass-rel">=</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo> <mo 
class="MathClass-bin">+</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-bin">&#x2212;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo> <mo 
class="MathClass-rel">=</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>a</mi><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo> <mo 
class="MathClass-bin">+</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi 
>b</mi><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 81--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
             <!--mstyle 
class="text"--><mtext  >&#x00A0;Recall&#x00A0;Law&#x00A0;of&#x00A0;Cosines:&#x00A0;</mtext><!--/mstyle--><msup><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-rel">=</mo> <msup><mrow 
><mi 
>a</mi></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-bin">+</mo> <msup><mrow 
><mi 
>b</mi></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-bin">&#x2212;</mo> <mn>2</mn><mi 
>a</mi><mi 
>b</mi><mi class="qopname">cos</mi><mo> &ApplyFunction;<!--FUNCTION APPLICATION--> </mo><!--nolimits--><mrow ><mo 
class="MathClass-open">(</mo><mrow><mi 
>&#x1D703;</mi></mrow><mo 
class="MathClass-close">)</mo></mrow>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 82--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
            <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x2212;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-rel">=</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-bin">+</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-bin">&#x2212;</mo> <mn>2</mn><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi class="qopname">cos</mi><mo> &ApplyFunction;<!--FUNCTION APPLICATION--> </mo><!--nolimits--><mrow ><mo 
class="MathClass-open">(</mo><mrow><mi 
>&#x1D703;</mi></mrow><mo 
class="MathClass-close">)</mo></mrow>
</math></td></tr></table>
   <table class="equation-star"><tr><td>

<!--l. 83--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
         <mrow ><mo 
class="MathClass-open">(</mo><mrow><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x2212;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></mrow><mo 
class="MathClass-close">)</mo></mrow> <mo 
class="MathClass-bin">&#x22C5;</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x2212;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></mrow><mo 
class="MathClass-close">)</mo></mrow> <mo 
class="MathClass-rel">=</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-bin">+</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-bin">&#x2212;</mo> <mn>2</mn><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi class="qopname">cos</mi><mo> &ApplyFunction;<!--FUNCTION APPLICATION--> </mo><!--nolimits--><mrow ><mo 
class="MathClass-open">(</mo><mrow><mi 
>&#x1D703;</mi></mrow><mo 
class="MathClass-close">)</mo></mrow>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 84--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
      <mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x2212;</mo> <mn>2</mn><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">+</mo> <mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-bin">+</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-bin">&#x2212;</mo> <mn>2</mn><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi class="qopname">cos</mi><mo> &ApplyFunction;<!--FUNCTION APPLICATION--> </mo><!--nolimits--><mrow ><mo 
class="MathClass-open">(</mo><mrow><mi 
>&#x1D703;</mi></mrow><mo 
class="MathClass-close">)</mo></mrow>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 85--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
       <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-bin">&#x2212;</mo> <mn>2</mn><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">+</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-rel">=</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-bin">+</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><msup><mrow 
><mo 
class="MathClass-rel">|</mo></mrow><mrow 
><mn>2</mn></mrow></msup 
> <mo 
class="MathClass-bin">&#x2212;</mo> <mn>2</mn><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi class="qopname">cos</mi><mo> &ApplyFunction;<!--FUNCTION APPLICATION--> </mo><!--nolimits--><mrow ><mo 
class="MathClass-open">(</mo><mrow><mi 
>&#x1D703;</mi></mrow><mo 
class="MathClass-close">)</mo></mrow>
</math></td></tr></table>
   <table class="equation-star"><tr><td>

<!--l. 86--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                      <mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi class="qopname">cos</mi><mo> &ApplyFunction;<!--FUNCTION APPLICATION--> </mo><!--nolimits--><mrow ><mo 
class="MathClass-open">(</mo><mrow><mi 
>&#x1D703;</mi></mrow><mo 
class="MathClass-close">)</mo></mrow>
</math></td></tr></table>
<!--l. 87--><p class="indent" >   Angles between vectors of any dimension are defined by
<!--l. 87--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x22C5;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mo 
class="MathClass-rel">|</mo><mi class="qopname">cos</mi><mo> &ApplyFunction;<!--FUNCTION APPLICATION--> </mo><!--nolimits--><mrow ><mo 
class="MathClass-open">(</mo><mrow><mi 
>&#x1D703;</mi></mrow><mo 
class="MathClass-close">)</mo></mrow></math>. Vectors are
perpendicular if the angle between them is 90 degrees, and orthoginal if their dot product is
<!--l. 88--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mn>0</mn></mrow><mo accent="true">&#x2192;</mo></mover></math>. Orthonormal means two
vectors&#x2019; dot product is <!--l. 89--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mn>0</mn></mrow><mo accent="true">&#x2192;</mo></mover></math>
and each of their magnitudes is 1.
</p>
    
</body>