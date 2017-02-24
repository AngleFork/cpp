



 

 

 

 

 

([C++](Cpp.htm)) [Answer of exercise \#9: No for-loops \#18](CppExerciseNoForLoopsAnswer18.htm)
===============================================================================================

 

This is the answer of [Exercise \#9: No
for-loops](CppExerciseNoForLoops.htm).

 

 

 

 

 

Question
--------

 

Replace the **[for](CppFor.htm)**-loop. You will need:

-   [std::greater.htm](CppGreater.htm)
-   A conditional [std::accumulate](CppAccumulate.htm)

 

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  ` int SumPositives(const std::vector<int>& v) {   const size_t sz = v.size();   int sum = 0;   for (size_t i=0; i!=sz; ++i)   {     if (v[i]>0) sum+=v[i];   }   return sum; }`
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

 

 

 

 

 

Answer
------

 

  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  ` template<typename InputIterator, typename ElementType, typename Predicate> const ElementType accumulate_if(   InputIterator first,   const InputIterator last,   ElementType init,   const Predicate predicate) {   for (; first != last; ++first)     if (predicate(*first)) init += *first;   return init; }  #include <vector> #include <functional>  int SumPositives(const std::vector<int>& v) {   return ::accumulate_if(v.begin(),v.end(),0,std::bind2nd(std::greater<int>(),0)); } `
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

 

 

 

 

 





 

[![Valid XHTML 1.0 Strict](valid-xhtml10.png){width="88"
height="31"}](http://validator.w3.org/check?uri=referer)