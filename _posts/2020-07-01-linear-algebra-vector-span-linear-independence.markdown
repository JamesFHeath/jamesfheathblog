---
layout: post
title:  "Linear Algebra: Linear Combinations, Span, Linear Independence"
categories: math
tags: linearalgebra math vectors
---
<body 
>
   <h3 class="likesectionHead"><a 
 id="x1-1000"></a>Linear Algebra: Linear Combination</h3>
<!--l. 13--><p class="noindent" >Linear combinations of vectors are sums of a set of vectors multilpied by constants. For example,
if we had <!--l. 14--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mn>0</mn><mo 
class="MathClass-punc">,</mo><mn>2</mn></mrow><mo 
class="MathClass-close">)</mo></mrow></math> and
<!--l. 14--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mn>4</mn><mo 
class="MathClass-punc">,</mo><mn>1</mn></mrow><mo 
class="MathClass-close">)</mo></mrow></math>, a linear combination
of them could be <!--l. 14--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mn>5</mn> <mo 
class="MathClass-bin">&#x2217;</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">+</mo> <mo 
class="MathClass-bin">&#x2212;</mo><mn>2</mn> <mo 
class="MathClass-bin">&#x2217;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mn>0</mn><mo 
class="MathClass-punc">,</mo><mn>1</mn><mn>0</mn></mrow><mo 
class="MathClass-close">)</mo></mrow> <mo 
class="MathClass-bin">+</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mo 
class="MathClass-bin">&#x2212;</mo><mn>8</mn><mo 
class="MathClass-punc">,</mo><mo 
class="MathClass-bin">&#x2212;</mo><mn>2</mn></mrow><mo 
class="MathClass-close">)</mo></mrow> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mo 
class="MathClass-bin">&#x2212;</mo><mn>8</mn><mo 
class="MathClass-punc">,</mo><mn>8</mn></mrow><mo 
class="MathClass-close">)</mo></mrow></math>.
</p><!--l. 16--><p class="noindent" >
</p>
   <h3 class="likesectionHead"><a 
 id="x1-2000"></a>Linear Algebra: Linear Independence</h3>
<!--l. 17--><p class="noindent" >We can imagine two vectors that point in the same direction, that their is a constant
<!--l. 17--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mi 
>c</mi></math>
that when multiplied by one of the vectors gets us the other vector.
<!--l. 18--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mn>1</mn><mo 
class="MathClass-punc">,</mo><mn>1</mn></mrow><mo 
class="MathClass-close">)</mo></mrow><mo 
class="MathClass-punc">,</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mn>2</mn><mo 
class="MathClass-punc">,</mo><mn>2</mn></mrow><mo 
class="MathClass-close">)</mo></mrow><mo 
class="MathClass-punc">,</mo><mn>2</mn> <mo 
class="MathClass-bin">&#x2217;</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></math> is an
example of <span 
class="cmti-10">linearly dependent </span>vectors. They lie on the same line. <span 
class="cmti-10">Linearly independent</span>
vectors require more than just a scaling, and therefore define two lines. The test for
linear independence/dependence is applicable in any number of dimensions:
<!--l. 21--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mrow ><mo 
class="MathClass-open">{</mo><mrow><msub><mrow 
><mover 
accent="true"><mrow 
><mi 
>v</mi></mrow><mo accent="true">&#x2192;</mo></mover></mrow><mrow 
><mn>1</mn></mrow></msub 
><mo 
class="MathClass-punc">,</mo><msub><mrow 
><mover 
accent="true"><mrow 
><mi 
>v</mi></mrow><mo accent="true">&#x2192;</mo></mover></mrow><mrow 
><mn>2</mn></mrow></msub 
><mo 
class="MathClass-punc">,</mo><mi 
class="MathClass-op">&#x2026;</mi><mo> &ApplyFunction;<!--FUNCTION APPLICATION--></mo><mo 
class="MathClass-punc">,</mo><msub><mrow 
><mover 
accent="true"><mrow 
><mi 
>v</mi></mrow><mo accent="true">&#x2192;</mo></mover></mrow><mrow 
><mi 
>n</mi></mrow></msub 
></mrow><mo 
class="MathClass-close">}</mo></mrow><mspace width="0.28em" class="thickpace"/><mo 
class="MathClass-rel">&#x21D4;</mo><mspace width="0.28em" class="thickpace"/><msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>1</mn></mrow></msub 
><msub><mrow 
><mover 
accent="true"><mrow 
><mi 
>v</mi></mrow><mo accent="true">&#x2192;</mo></mover></mrow><mrow 
><mn>1</mn></mrow></msub 
> <mo 
class="MathClass-bin">+</mo> <msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>2</mn></mrow></msub 
><msub><mrow 
><mover 
accent="true"><mrow 
><mi 
>v</mi></mrow><mo accent="true">&#x2192;</mo></mover></mrow><mrow 
><mn>2</mn></mrow></msub 
> <mo 
class="MathClass-bin">+</mo> <mo 
class="MathClass-rel">&#x22EF;</mo> <mo 
class="MathClass-bin">+</mo> <msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mi 
>n</mi></mrow></msub 
><msub><mrow 
><mover 
accent="true"><mrow 
><mi 
>v</mi></mrow><mo accent="true">&#x2192;</mo></mover></mrow><mrow 
><mi 
>n</mi></mrow></msub 
> <mo 
class="MathClass-rel">=</mo> <mover 
accent="true"><mrow 
><mn>0</mn></mrow><mo accent="true">&#x2192;</mo></mover></math> where at
least one <!--l. 21--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mi 
>c</mi></math>
is non-zero means the vectors are <span 
class="cmti-10">linearly dependant</span>. </p><table class="equation-star"><tr><td>
<!--l. 22--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                        <mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mn>1</mn><mo 
class="MathClass-punc">,</mo><mn>1</mn></mrow><mo 
class="MathClass-close">)</mo></mrow><mo 
class="MathClass-punc">,</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mn>2</mn><mo 
class="MathClass-punc">,</mo><mn>2</mn></mrow><mo 
class="MathClass-close">)</mo></mrow>
</math></td></tr></table>
   <table class="equation-star"><tr><td>

<!--l. 23--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                      <msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>1</mn></mrow></msub 
><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">+</mo> <msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>2</mn></mrow></msub 
><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mover 
accent="true"><mrow 
><mn>0</mn></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mn>0</mn><mo 
class="MathClass-punc">,</mo><mn>0</mn></mrow><mo 
class="MathClass-close">)</mo></mrow>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 24--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                            <msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>1</mn></mrow></msub 
> <mo 
class="MathClass-bin">+</mo> <mn>2</mn><msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>2</mn></mrow></msub 
> <mo 
class="MathClass-rel">=</mo> <mn>0</mn>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 25--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                             <msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>1</mn></mrow></msub 
> <mo 
class="MathClass-rel">=</mo> <mo 
class="MathClass-bin">&#x2212;</mo><mn>2</mn><msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>2</mn></mrow></msub 
>
</math></td></tr></table>
   <table class="equation-star"><tr><td>

<!--l. 26--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                    <msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>1</mn></mrow></msub 
> <mo 
class="MathClass-rel">=</mo> <mn>5</mn><mo 
class="MathClass-punc">,</mo><!--mstyle 
class="text"--><mtext  >&#x00A0;arbitrary&#x00A0;choice&#x00A0;for&#x00A0;</mtext><!--/mstyle--><msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>1</mn></mrow></msub 
>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 27--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                             <mo 
class="MathClass-bin">&#x2212;</mo><mn>2</mn><msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>2</mn></mrow></msub 
> <mo 
class="MathClass-rel">=</mo> <mn>5</mn>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 28--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                             <msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>2</mn></mrow></msub 
> <mo 
class="MathClass-rel">=</mo> <mo 
class="MathClass-bin">&#x2212;</mo><mfrac><mrow 
><mn>5</mn></mrow>
<mrow 
><mn>2</mn></mrow></mfrac>
</math></td></tr></table>
   <table class="equation-star"><tr><td>

<!--l. 29--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                            <msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>1</mn></mrow></msub 
> <mo 
class="MathClass-bin">+</mo> <mn>2</mn><msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>2</mn></mrow></msub 
> <mo 
class="MathClass-rel">=</mo> <mn>0</mn>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 30--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                           <mn>5</mn> <mo 
class="MathClass-bin">+</mo> <mn>2</mn><mrow ><mo 
class="MathClass-open">(</mo><mrow><mo 
class="MathClass-bin">&#x2212;</mo><mfrac><mrow 
><mn>5</mn></mrow>
<mrow 
><mn>2</mn></mrow></mfrac> <mo 
class="MathClass-rel">=</mo> <mn>0</mn></mrow><mo 
class="MathClass-close">)</mo></mrow>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 31--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                            <mn>5</mn> <mo 
class="MathClass-bin">+</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mo 
class="MathClass-bin">&#x2212;</mo><mn>5</mn></mrow><mo 
class="MathClass-close">)</mo></mrow> <mo 
class="MathClass-rel">=</mo> <mn>0</mn>
</math></td></tr></table>
<!--l. 32--><p class="indent" >   Any non-zero constant can satisfy this equation
<!--l. 32--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>1</mn></mrow></msub 
> <mo 
class="MathClass-bin">+</mo> <mn>2</mn><msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>2</mn></mrow></msub 
> <mo 
class="MathClass-rel">=</mo> <mn>0</mn></math>, so we
know <!--l. 32--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-punc">,</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></math>
are <span 
class="cmti-10">linearly dependent</span>. </p><table class="equation-star"><tr><td>

<!--l. 33--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                        <mover 
accent="true"><mrow 
><mi 
>c</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mn>2</mn><mo 
class="MathClass-punc">,</mo><mn>1</mn></mrow><mo 
class="MathClass-close">)</mo></mrow><mo 
class="MathClass-punc">,</mo><mover 
accent="true"><mrow 
><mi 
>d</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mn>3</mn><mo 
class="MathClass-punc">,</mo><mn>2</mn></mrow><mo 
class="MathClass-close">)</mo></mrow>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 34--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                           <mn>2</mn><msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>1</mn></mrow></msub 
> <mo 
class="MathClass-bin">+</mo> <mn>3</mn><msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>2</mn></mrow></msub 
> <mo 
class="MathClass-rel">=</mo> <mn>0</mn>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 35--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                            <msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>1</mn></mrow></msub 
> <mo 
class="MathClass-bin">+</mo> <mn>2</mn><msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>2</mn></mrow></msub 
> <mo 
class="MathClass-rel">=</mo> <mn>0</mn>
</math></td></tr></table>
   <table class="equation-star"><tr><td>

<!--l. 36--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                            <mn>2</mn><msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>1</mn></mrow></msub 
> <mo 
class="MathClass-rel">=</mo> <mo 
class="MathClass-bin">&#x2212;</mo><mn>3</mn><msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>2</mn></mrow></msub 
>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 37--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                            <msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>1</mn></mrow></msub 
> <mo 
class="MathClass-rel">=</mo> <mo 
class="MathClass-bin">&#x2212;</mo><mfrac><mrow 
><mn>3</mn><msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>2</mn></mrow></msub 
></mrow>
  <mrow 
><mn>2</mn></mrow></mfrac>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 38--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                          <mo 
class="MathClass-bin">&#x2212;</mo><mfrac><mrow 
><mn>3</mn><msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>2</mn></mrow></msub 
></mrow>
  <mrow 
><mn>2</mn></mrow></mfrac>  <mo 
class="MathClass-bin">+</mo> <mn>2</mn><msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>2</mn></mrow></msub 
> <mo 
class="MathClass-rel">=</mo> <mn>0</mn>
</math></td></tr></table>
   <table class="equation-star"><tr><td>

<!--l. 39--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                              <mfrac><mrow 
><msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>2</mn></mrow></msub 
></mrow>
 <mrow 
><mn>2</mn></mrow></mfrac> <mo 
class="MathClass-rel">=</mo> <mn>0</mn>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 40--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                              <msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>2</mn></mrow></msub 
> <mo 
class="MathClass-rel">=</mo> <mn>0</mn>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 41--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                           <msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>1</mn></mrow></msub 
> <mo 
class="MathClass-bin">+</mo> <mn>2</mn><mrow ><mo 
class="MathClass-open">(</mo><mrow><mn>0</mn></mrow><mo 
class="MathClass-close">)</mo></mrow> <mo 
class="MathClass-rel">=</mo> <mn>0</mn>
</math></td></tr></table>
   <table class="equation-star"><tr><td>

<!--l. 42--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                             <msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>1</mn></mrow></msub 
> <mo 
class="MathClass-bin">+</mo> <mn>0</mn> <mo 
class="MathClass-rel">=</mo> <mn>0</mn>
</math></td></tr></table>
   <table class="equation-star"><tr><td>
<!--l. 43--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="block" class="equation">
                              <msub><mrow 
><mi 
>c</mi></mrow><mrow 
><mn>1</mn></mrow></msub 
> <mo 
class="MathClass-rel">=</mo> <mn>0</mn>
</math></td></tr></table>
<!--l. 44--><p class="indent" >   0&#x2019;s are the only values that satisfy these equations, so we know
<!--l. 44--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>c</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mn>2</mn><mo 
class="MathClass-punc">,</mo><mn>1</mn></mrow><mo 
class="MathClass-close">)</mo></mrow><mo 
class="MathClass-punc">,</mo><mover 
accent="true"><mrow 
><mi 
>d</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mn>3</mn><mo 
class="MathClass-punc">,</mo><mn>2</mn></mrow><mo 
class="MathClass-close">)</mo></mrow></math> are
<span 
class="cmti-10">linearly independent</span>
</p><!--l. 47--><p class="noindent" >
</p>
   <h3 class="likesectionHead"><a 
 id="x1-3000"></a>Linear Algebra: Span and Basis</h3>
<!--l. 48--><p class="noindent" ><!--l. 48--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mi 
>C</mi> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">{</mo><mrow><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x2217;</mo> <mi 
>c</mi><mn>1</mn> <mo 
class="MathClass-bin">+</mo> <mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x2217;</mo> <mi 
>c</mi><mn>2</mn><mo 
class="MathClass-rel">|</mo><mi 
>c</mi><mn>1</mn><mo 
class="MathClass-punc">,</mo><mi 
>c</mi><mn>2</mn> <mo 
class="MathClass-rel">&#x2208;</mo> <mi 
>&#x211D;</mi></mrow><mo 
class="MathClass-close">}</mo></mrow></math> defines all the linear
combinations of <!--l. 48--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover></math>,
<!--l. 48--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></math> and is the
&#x201D;span&#x201D; of <!--l. 48--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover></math>
and <!--l. 48--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></math>. A
<span 
class="cmti-10">Span </span>will either define a single line if the vectors are <span 
class="cmti-10">linearly dependent </span>or a vector space
<!--l. 49--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><msup><mrow 
><mi 
>&#x211D;</mi></mrow><mrow 
><mi 
>n</mi></mrow></msup 
></math> if all vectors
<!--l. 49--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mi 
>S</mi> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">{</mo><mrow><msub><mrow 
><mover 
accent="true"><mrow 
><mi 
>v</mi></mrow><mo accent="true">&#x2192;</mo></mover></mrow><mrow 
><mn>1</mn></mrow></msub 
><mo 
class="MathClass-punc">,</mo><msub><mrow 
><mover 
accent="true"><mrow 
><mi 
>v</mi></mrow><mo accent="true">&#x2192;</mo></mover></mrow><mrow 
><mn>2</mn></mrow></msub 
><mo 
class="MathClass-punc">,</mo><mi 
class="MathClass-op">&#x2026;</mi><mo> &ApplyFunction;<!--FUNCTION APPLICATION--></mo><mo 
class="MathClass-punc">,</mo><msub><mrow 
><mover 
accent="true"><mrow 
><mi 
>v</mi></mrow><mo accent="true">&#x2192;</mo></mover></mrow><mrow 
><mi 
>n</mi></mrow></msub 
></mrow><mo 
class="MathClass-close">}</mo></mrow></math> are <span 
class="cmti-10">linearly</span>
<span 
class="cmti-10">independent</span>. <!--l. 50--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mi 
>S</mi><mi 
>p</mi><mi 
>a</mi><mi 
>n</mi><mrow ><mo 
class="MathClass-open">(</mo><mrow><mrow ><mo 
class="MathClass-open">{</mo><mrow><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-punc">,</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></mrow><mo 
class="MathClass-close">}</mo></mrow></mrow><mo 
class="MathClass-close">)</mo></mrow> <mo 
class="MathClass-rel">=</mo> <msup><mrow 
><mi 
>&#x211D;</mi></mrow><mrow 
><mn>2</mn></mrow></msup 
><mspace width="0.28em" class="thickpace"/><mo 
class="MathClass-rel">&#x21D4;</mo><mspace width="0.28em" class="thickpace"/><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-punc">,</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></math>
are <span 
class="cmti-10">linearly independent</span>. If they are <span 
class="cmti-10">linearly independent</span>, then the vectors
<!--l. 51--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-punc">,</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></math> form a <span 
class="cmti-10">basis </span>of
<!--l. 51--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><msup><mrow 
><mi 
>&#x211D;</mi></mrow><mrow 
><mn>2</mn></mrow></msup 
></math>, meaning the linear

combinations of <!--l. 51--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-punc">,</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></math> describe
EVERY vector in <!--l. 51--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><msup><mrow 
><mi 
>&#x211D;</mi></mrow><mrow 
><mn>2</mn></mrow></msup 
></math>.
</p>
    
</body> 
