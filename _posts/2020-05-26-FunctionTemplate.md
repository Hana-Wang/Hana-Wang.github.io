---
#layout: post
title:  "Function Templates"
description: An example post which shows code rendering.
date:   2019-05-26
categories: "Templates"
---
<p> Generic Programming is that there is no specified data types when using algorithms. It means algorithm can apply to many types of data
structures.</p>
<p> </p>

<p> Benefits: generic programming can reduce the repeating codes. </p>

<p> </p>

<p> There are two types of templates, one is Function Template, the other is Class Template</p>


<h2>Function Templates vs Overloaded Functions </h2>

<p>Overloaded Functions</p>

<ul>

<p> </p>
<li> Overloaded functions are functions which have the same function name but have different parameters. </li>

<p> </p>
<li> Different parameters means either overloaded functions have a different number of parameters  or any of their parameters are of a different typle.</li>

<p> </p>
<li> A function cannot be overloaded only by its return type, it should have different parameters with another overloaded function.</li>

</ul>

<p> </p>

<p>Function Templates</p>

<ul>

<p> </p>
<li> Two functions with the same name and having the same function body, C++ can define these functions with generic types and has a same algorithm, called function templates. </li>

<p> </p>
<li> When defining a function template, a keyword 'template' is used before defining the function to indicate you are defining a function template.</li>

<p> </p>
<li>A function template has a series of template parameters, which can be regular types or generic type parameters by specifying the keywords either the 'class' or 'typename' followed by an identifier.</li>

<p> </p>

<li>

<p> Syntax </p>

{% highlight ruby %}
template <class Type1, class Type2, ...> // can use keyword 'class' or 'typename'
Type2 FunTemplateName (Type1 a, Type1 b, Type2 c)
{
   function body;
}
{% endhighlight %} </li>

</ul>

<p> </p>

<p>Examples of function templates</p>
<ul>
<li>
{% highlight ruby %}
// Task1: Define a function template that do swap of two same type of variables.
// There is one type parameter called 'T'.

template <class T>  // can use keyword 'class' or 'typename'
void Swap ( T& a, T& b)
{
   T tmp = x;
   x = y;
   y = tmp;
}
{% endhighlight %}</li>

<li>
{% highlight ruby %}
// Task2: Define a function template that do swap of two different types of variables.
//There are two type parameters; one is called 'T1', the other is called 'T2'.

template <class T1, class T2>  // can use keyword 'class' or 'typename'
void Swap ( T1& a, T2& b)
{
   T tmp = x;
   x = y;
   y = tmp;
}
{% endhighlight %}</li>
</ul>

<h2>Question: how to use function templates? </h2>
<p>Example codes:</p>
{% highlight ruby %}
// Task: use the function template in the main function.

int main(){
    int n=1, m=2;
    swap(n, m);
    // the compiler automatically generate a template function "void swap(int& x, int& y)"
    // which is instantiated by replacing 'T' with 'int' in the function template "void swap(T& x, T& y)"".

    double f = 1.3, g =2.1;
    swap(f, g);  
    // the compiler generates a function to use, it is "void swap(double & x, double& y)"  

    swap(f, m);
    // the compiler generates a function to use, it is "void swap(double& x, int& y)"
    // which is done by replacing 'T1' by 'double' and 'T2' by 'int'
}

{% endhighlight %}

<p> Notes: </p>
<ul>
<li>
<p>From the example codes, function template can be overloaded if their template parameters (type parameters) are different, which is because they have a different number of template parameters. </p> </li>

<li>
<p>Recall the regular overloaded functions in C++, they are different functions with the same name but their function parameters are different; either because they have a different number of parameters, or because any of their parameters are of a different type. </p> </li>

</ul>



<h2>Question: how does C++ knows which function or function template to call?  </h2>

<p> </p>
<p>There is a calling order for C++ compiler when calling overloaded functions, function templates. The choosing order for compiler is as follows.</p>

<ul>
<li>
<p>1st, Find a function where its parameters are matched exactly; a function not by instantiation of the function template.  </p> </li>

<li>
<p>2nd, Find a function template where its template parameters are matched.</p> </li>

<li>
<p>3rd, Find a function where the calling function's parameters type can automatically convert to its function parameters and be matched.</p> </li>

<li>
<p>4th, if no one suitable function or function template can be found to match the calling function's parameters, then, the C++ compiler report the function calling error.</p> </li>

</ul>

<p>An example code that shows the calling order of function templates, overloaded functions.</p>

The source codes are available in Github, the repository "........" .
