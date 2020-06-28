---
layout: post
title:  "Linear Algebra: Vector Addition & Scaling"
categories: math
tags: linearalgebra math vectors
---

<?xml version="1.0" encoding="iso-8859-1" ?> 
<body 
>
   <h3 class="likesectionHead"><a 
 id="x1-1000"></a>Linear Algebra: Vector Addition and Scaling</h3>
<!--l. 12--><p class="noindent" >
</p>
   <h3 class="likesectionHead"><a 
 id="x1-2000"></a>Vector Addition Definition</h3>
<!--l. 13--><p class="noindent" >Vector addition is simply adding two vectors together to generate a third vector. For
example, <!--l. 14--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">+</mo> <mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mover 
accent="true"><mrow 
><mi 
>c</mi></mrow><mo accent="true">&#x2192;</mo></mover></math>
if we say <!--l. 14--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
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
class="MathClass-close">)</mo></mrow><mo 
class="MathClass-punc">,</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
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
class="MathClass-close">)</mo></mrow></math>
then <!--l. 14--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">+</mo> <mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><msub><mrow 
><mi 
>a</mi></mrow><mrow 
><mn>1</mn></mrow></msub 
> <mo 
class="MathClass-bin">+</mo> <msub><mrow 
><mi 
>b</mi></mrow><mrow 
><mn>1</mn></mrow></msub 
><mo 
class="MathClass-punc">,</mo><msub><mrow 
><mi 
>a</mi></mrow><mrow 
><mn>2</mn></mrow></msub 
> <mo 
class="MathClass-bin">+</mo> <msub><mrow 
><mi 
>b</mi></mrow><mrow 
><mn>2</mn></mrow></msub 
><mo 
class="MathClass-punc">,</mo><mi 
class="MathClass-op">&#x2026;</mi><mo> &ApplyFunction;<!--FUNCTION APPLICATION--></mo><mo 
class="MathClass-punc">,</mo><msub><mrow 
><mi 
>a</mi></mrow><mrow 
><mi 
>n</mi></mrow></msub 
> <mo 
class="MathClass-bin">+</mo> <msub><mrow 
><mi 
>b</mi></mrow><mrow 
><mi 
>n</mi></mrow></msub 
></mrow><mo 
class="MathClass-close">)</mo></mrow></math>.
</p><!--l. 16--><p class="noindent" >
</p>
   <h3 class="likesectionHead"><a 
 id="x1-3000"></a>Vector Addition Visually</h3>
<!--l. 17--><p class="noindent" >Vector addition can be visualed in 2-d space using the head-to-tail technique. Head-to-tail is
simply putting the tail of the second vector on the head of the first vector. Let&#x2019;s say we have
<!--l. 19--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>a</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mn>1</mn><mo 
class="MathClass-punc">,</mo><mn>3</mn></mrow><mo 
class="MathClass-close">)</mo></mrow><mo 
class="MathClass-punc">,</mo><mover 
accent="true"><mrow 
><mi 
>b</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mn>3</mn><mo 
class="MathClass-punc">,</mo><mn>4</mn></mrow><mo 
class="MathClass-close">)</mo></mrow></math>. We know that the
resulting vector is <!--l. 20--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mrow ><mo 
class="MathClass-open">(</mo><mrow><mn>1</mn> <mo 
class="MathClass-bin">+</mo> <mn>3</mn><mo 
class="MathClass-punc">,</mo><mn>3</mn> <mo 
class="MathClass-bin">+</mo> <mn>4</mn></mrow><mo 
class="MathClass-close">)</mo></mrow> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><mn>4</mn><mo 
class="MathClass-punc">,</mo><mn>7</mn></mrow><mo 
class="MathClass-close">)</mo></mrow></math>.
</p>
   <hr class="figure" /><div class="figure" 
>


<!--l. 24--><p class="noindent" ></p><!--l. 26--><p class="noindent" ><img 
src="/images/vector_add_1.png" alt="PIC"  
width="207" height="207"  /> <a 
 id="x1-3001r1"></a>
<span 
class="cmr-9">(a) (1 + 3, 3 + 4) = (4, 7)</span>
</p><!--l. 30--><p class="noindent" ><img 
src="/images/vector_add_2.png" alt="PIC"  
width="207" height="207"  /> <a 
 id="x1-3002r2"></a>
<span 
class="cmr-9">(b) (1 + 3, 3 + 4) = (4, 7) Head to Tail</span>

</p>
   </div><hr class="endfigure" />
   <h3 class="likesectionHead"><a 
 id="x1-4000"></a>Vector Scaling</h3>
<!--l. 38--><p class="noindent" >Vector scaling is multiplying a vector <!--l. 38--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>v</mi></mrow><mo accent="true">&#x2192;</mo></mover></math>
by a constant <!--l. 38--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mi 
>c</mi></math> to get
a vector scaled with <!--l. 38--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mi 
>c</mi></math>.
Scaling can be done for a vector of any number of dimensions. If we have
<!--l. 40--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>v</mi></mrow><mo accent="true">&#x2192;</mo></mover></math> and
constant <!--l. 40--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mi 
>c</mi></math>,
then <!--l. 40--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mover 
accent="true"><mrow 
><mi 
>v</mi></mrow><mo accent="true">&#x2192;</mo></mover> <mo 
class="MathClass-bin">&#x2217;</mo> <mi 
>c</mi> <mo 
class="MathClass-rel">=</mo> <mrow ><mo 
class="MathClass-open">(</mo><mrow><msub><mrow 
><mi 
>v</mi></mrow><mrow 
><mn>1</mn></mrow></msub 
> <mo 
class="MathClass-bin">&#x2217;</mo> <mi 
>c</mi><mo 
class="MathClass-punc">,</mo><msub><mrow 
><mi 
>v</mi></mrow><mrow 
><mn>2</mn></mrow></msub 
> <mo 
class="MathClass-bin">&#x2217;</mo> <mi 
>c</mi><mo 
class="MathClass-punc">,</mo><mi 
class="MathClass-op">&#x2026;</mi><mo> &ApplyFunction;<!--FUNCTION APPLICATION--></mo><mo 
class="MathClass-punc">,</mo><msub><mrow 
><mi 
>v</mi></mrow><mrow 
><mi 
>n</mi></mrow></msub 
> <mo 
class="MathClass-bin">&#x2217;</mo> <mi 
>c</mi></mrow><mo 
class="MathClass-close">)</mo></mrow></math>.
</p><!--l. 42--><p class="noindent" >
</p>
   <h3 class="likesectionHead"><a 
 id="x1-5000"></a>Vector Scaling Visually</h3>
<!--l. 43--><p class="noindent" >Visually, vector scaling will result in a larger or smaller vector
pointing in the same direction if multiplied by a positive
<!--l. 43--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mi 
>c</mi></math>, or a
larger or smaller vector pointing in the opposite direction if multiplied by a negative
<!--l. 43--><math 
 xmlns="http://www.w3.org/1998/Math/MathML" display="inline" ><mi 
>c</mi></math>.
</p>
   <hr class="figure" /><div class="figure" 
>


<!--l. 47--><p class="noindent" ></p><!--l. 49--><p class="noindent" ><img 
src="/images/vector_scale_1.png" alt="PIC"  
width="207" height="207"  /> <a 
 id="x1-5001r1"></a>
<span 
class="cmr-9">(a) (1,3)</span>
</p><!--l. 53--><p class="noindent" ><img 
src="/images/vector_scale_2.png" alt="PIC"  
width="207" height="207"  /> <a 
 id="x1-5002r2"></a>
<span 
class="cmr-9">(b) (1,3) * 3 = (3,9)</span>
</p><!--l. 57--><p class="noindent" ><img 
src="/images/vector_scale_3.png" alt="PIC"  
width="207" height="207"  /> <a 
 id="x1-5003r3"></a>
<span 
class="cmr-9">(c) (1,3) * -3 = (-3,-9)</span>

</p>
   </div><hr class="endfigure" />
    
</body> 