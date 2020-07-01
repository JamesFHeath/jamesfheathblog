---
layout: post
title:  "Linear Algebra: Subspaces"
categories: math
tags: linearalgebra math vectors
---

<body 
>
   <h3 class="likesectionHead"><a 
 id="x1-1000"></a>Linear Algebra: Subspaces</h3>
<!--l. 13--><p class="noindent" ><span 
class="cmti-10">Linear Subspaces </span>are subsets of vector spaces that have 3 specific properties. A set of
vectors <!--l. 14--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mi 
>&#x03D2;</mi></math>
is a subspace if...
     </p><ol  class="enumerate1" >
     <li 
  class="enumerate" id="x1-1002x1"><!--l. 16--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mi 
>&#x03D2;</mi></math>
     contains the zero vector <!--l. 16--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mn>0</mn></mrow><mo accent="true">&#x2192;</mo></mover></math>
     </li>
     <li 
  class="enumerate" id="x1-1004x2">Closed under scalar multiplication. <!--l. 17--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>x</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">&#x2208;</mo> <mi 
>&#x03D2;</mi><mspace width="0.28em" class="thickpace"/><mo 
class="MathClass-rel">&#x21D2;</mo><mspace width="0.28em" class="thickpace"/><mi 
>c</mi><mover 
accent="true"><mrow 
><mi 
>x</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">&#x2208;</mo> <mi 
>&#x03D2;</mi><mi 
class="MathClass-op">&#x2200;</mi><mo> &ApplyFunction;<!--FUNCTION APPLICATION--></mo><mi 
>c</mi> <mo 
class="MathClass-rel">&#x2208;</mo> <mi 
>&#x211D;</mi></math>.
     </li>
     <li 
  class="enumerate" id="x1-1006x3">Closed under addition. <!--l. 18--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>x</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">&#x2208;</mo> <mi 
>&#x03D2;</mi> <mo 
class="MathClass-bin">&#x2227;</mo><mover 
accent="true"><mrow 
><mi 
>y</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">&#x2208;</mo> <mi 
>&#x03D2;</mi><mspace width="0.28em" class="thickpace"/><mo 
class="MathClass-rel">&#x21D2;</mo><mspace width="0.28em" class="thickpace"/><mover 
accent="true"><mrow 
><mi 
>x</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">+</mo> <mover 
accent="true"><mrow 
><mi 
>y</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">&#x2208;</mo> <mi 
>&#x03D2;</mi></math>.</li></ol>
<!--l. 20--><p class="noindent" >A trivial example of a subspace is just a set
<!--l. 20--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mi 
>V</mi> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">{</mo><mrow><mover 
accent="true"><mrow 
><mn>0</mn></mrow><mo accent="true">&#x2192;</mo></mover></mrow><mo 
class="MathClass-close">}</mo></mrow></math>. It contains
the zero vector, and any addition and scalar multiplication will just return to the zero vector.
What about <!--l. 22--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mi 
>S</mi> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">{</mo><mrow><mrow ><mo 
class="MathClass-open">(</mo><mrow><mi 
>x</mi><mo 
class="MathClass-punc">,</mo><mi 
>y</mi></mrow><mo 
class="MathClass-close">)</mo></mrow> <mo 
class="MathClass-rel">&#x2208;</mo> <msup><mrow 
><mi 
>&#x211D;</mi></mrow><mrow 
><mn>2</mn></mrow></msup 
><mo 
class="MathClass-rel">|</mo><mi 
>x</mi> <mo 
class="MathClass-rel">&#x003E;</mo><mo 
class="MathClass-rel">=</mo> <mn>0</mn></mrow><mo 
class="MathClass-close">}</mo></mrow></math>.
This set defines everything in quadrant I and IV, to the right of the y-axis. It
contains the zero vector, and any two vectors added together will stay in the
subspace. The reason this is not a valid subspace is that scalar multiplication by a
negative number can generate vectors outside of the set.
</p><!--l. 27--><p class="noindent" >
</p>
   <h3 class="likesectionHead"><a 
 id="x1-2000"></a>Span and Basis of a Subspace</h3>
<!--l. 28--><p class="noindent" >Span is useful for generating subspaces. A span of linearly dependent vectors will create a line that
is a subspace of <!--l. 29--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><msup><mrow 
><mi 
>&#x211D;</mi></mrow><mrow 
><mi 
>n</mi></mrow></msup 
></math>.
A span of <!--l. 30--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mi 
>n</mi></math>
linearly independent vectors will create a subspace of
<!--l. 30--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><msup><mrow 
><mi 
>&#x211D;</mi></mrow><mrow 
><mi 
>n</mi></mrow></msup 
></math> that is <span 
class="cmti-10">also </span>spans
<!--l. 30--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><msup><mrow 
><mi 
>&#x211D;</mi></mrow><mrow 
><mi 
>n</mi></mrow></msup 
></math>. The basis of a
vector space <!--l. 31--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><msup><mrow 
><mi 
>&#x211D;</mi></mrow><mrow 
><mi 
>n</mi></mrow></msup 
></math> is
the minimum number of linearly independent vectors whose linear combinations can create all
vectors in <!--l. 31--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><msup><mrow 
><mi 
>&#x211D;</mi></mrow><mrow 
><mi 
>n</mi></mrow></msup 
></math>. The
standard basis of <!--l. 32--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><msup><mrow 
><mi 
>&#x211D;</mi></mrow><mrow 
><mn>2</mn></mrow></msup 
></math>
is (0, 1) and (1, 0). The number of vectors in the basis is the same as the number of
dimensions in the vector space.
</p>
    
</body>