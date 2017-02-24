



 

 

 

 

 

([C++](Cpp.htm)) [std::minus](CppMinus.htm)
===========================================

 

[std::minus](CppMinus.htm) is a [functor](CppFunctor.htm) that
encapsulates [operator-](CppOperatorMinus.htm).

 

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  ` #include <vector> #include <algorithm> #include <numeric>  const std::vector<int> MinusTwo(const std::vector<int>& v) {   std::vector<int> v_new;   std::transform(v.begin(),v.end(),std::back_inserter(v_new),     std::bind2nd(std::minus<int>(),2));   return v_new; }`
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

 

 

 

 

 





 

[![Valid XHTML 1.0 Strict](valid-xhtml10.png){width="88"
height="31"}](http://validator.w3.org/check?uri=referer)