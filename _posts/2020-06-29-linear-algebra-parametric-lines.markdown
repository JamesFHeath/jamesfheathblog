---
layout: post
title:  "Linear Algebra: Parametric Representation of Lines"
categories: math
tags: linearalgebra math vectors
---

   <h3 class="likesectionHead"><a 
 id="x1-1000"></a>Linear Algebra: Parametric Representation of a Line</h3>
<!--l. 13--><p class="noindent" >Lines in 2-d space can be represented by
<!--l. 13--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mi 
>y</mi> <mo 
class="MathClass-rel">=</mo> <mi 
>m</mi><mi 
>x</mi> <mo 
class="MathClass-bin">+</mo> <mi 
>b</mi></math>, but
with higher dimensional spaces it can help to generalize the formula for a line. If we have
<!--l. 14--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover></math>, we can
define a set <!--l. 14--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mi 
>S</mi> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">{</mo><mrow><mi 
>c</mi> <mo 
class="MathClass-bin">&#x2217;</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mi 
>c</mi> <mo 
class="MathClass-rel">&#x2208;</mo> <mi 
>&#x211D;</mi></mrow><mo 
class="MathClass-close">}</mo></mrow></math>.
Taking all real numbers and multiplying them by our vector give us a set of vectors that span
the line of <!--l. 15--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover></math>.
This set notation can be used to create a line from a vector of any dimension.
</p><!--l. 18--><p class="noindent" >
</p>
   <h3 class="likesectionHead"><a 
 id="x1-2000"></a>Linear Algebra: Defining Parallel Lines</h3>
<!--l. 19--><p class="noindent" >Defining a parallel line becomes simple, especially when dealing with
many dimensions where &#x201D;slope&#x201D; isn&#x2019;t intuitive. Let&#x2019;s say we have
<!--l. 20--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mn>2</mn><mo 
class="MathClass-punc">,</mo><mn>1</mn></mrow><mo 
class="MathClass-close">)</mo></mrow></math>,<!--l. 20--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mn>0</mn><mo 
class="MathClass-punc">,</mo><mn>3</mn></mrow><mo 
class="MathClass-close">)</mo></mrow></math>
and we want a parallel line from <!--l. 20--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mi 
>S</mi> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">{</mo><mrow><mi 
>c</mi> <mo 
class="MathClass-bin">&#x2217;</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mi 
>c</mi> <mo 
class="MathClass-rel">&#x2208;</mo> <mi 
>&#x211D;</mi></mrow><mo 
class="MathClass-close">}</mo></mrow></math>
that passes through the point defined by
<!--l. 20--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></math>. What we can do is take
our set <!--l. 21--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mi 
>S</mi></math> and modify it
to be the parallel line <!--l. 21--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mi 
>P</mi> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">{</mo><mrow><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">+</mo> <mi 
>t</mi> <mo 
class="MathClass-bin">&#x2217;</mo><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover><mo 
class="MathClass-rel">|</mo><mi 
>t</mi> <mo 
class="MathClass-rel">&#x2208;</mo> <mi 
>&#x211D;</mi></mrow><mo 
class="MathClass-close">}</mo></mrow></math>.
This is taking all the point defined on our line by
<!--l. 22--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mi 
>S</mi></math>, and offsetting them by
<!--l. 22--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></math> over to a parallel line
that passes through <!--l. 22--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></math>,
as seen in the graph below. This definition extends to vectors of any dimension.
</p><!--l. 27--><p class="noindent" >
</p>

<div style="text-align: center"><img src="/images/vector_parallel_translation.png" alt="Parallel Lines"/></div>
   <h3 class="likesectionHead"><a 
 id="x1-3000"></a>Linear Algebra: Defining Lines through 2 Vectors</h3>
<!--l. 28--><p class="noindent" >Defining a line that passes through the endpoints of 2 vectors is also
simple with our set definition of a line. All we need is to translate either
<!--l. 29--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover></math> or
<!--l. 29--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></math> by all the points on
the line defined by <!--l. 29--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x2212;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></math>,
which is just the vector between their endpoints. Formula is
<!--l. 30--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mi 
>L</mi> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">{</mo><mrow><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">+</mo> <mi 
>t</mi><mrow ><mo 
class="MathClass-open">(</mo><mrow><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x2212;</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover></mrow><mo 
class="MathClass-close">)</mo></mrow><mo 
class="MathClass-rel">|</mo><mi 
>t</mi> <mo 
class="MathClass-rel">&#x2208;</mo> <mi 
>&#x211D;</mi></mrow><mo 
class="MathClass-close">}</mo></mrow></math>.
</p>
<div style="text-align: center"><img src="/images/vector_line_through_2_vectors.png" alt="Line Through Two Vectors"/></div>