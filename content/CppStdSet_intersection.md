



 

 

 

 

 

([C++](Cpp.htm)) [std::set\_intersection](CppSet_intersection.htm)
==================================================================

 

[std::set\_intersection](CppSet_intersection.htm) is an
[STL](CppStl.htm) [algorithm](CppAlgorithm.htm) to create the
intersection set of two sets (stored in any type of
[container](CppContainer.htm)).

 

  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  ` #include <algorithm> #include <cassert> #include <iostream> #include <iterator> #include <vector>  int main() {   //v contains all values from zero to ten   std::vector<int> v;   v.push_back(0);   v.push_back(1);   v.push_back(2);   v.push_back(3);   v.push_back(4);   v.push_back(5);   v.push_back(6);   v.push_back(7);   v.push_back(8);   v.push_back(9);    //w contains all squares from 1 to an including 25   std::vector<int> w;   w.push_back( 1);   w.push_back( 4);   w.push_back( 9);   w.push_back(16);   w.push_back(25);    //x is the intersection of v and w   std::vector<int> x;    std::set_intersection(v.begin(),v.end(),w.begin(),w.end(),     std::back_inserter(x));    //so x contains all three squares between zero to ten   assert(x.size() == 3);   assert(x[0] == 1);   assert(x[1] == 4);   assert(x[2] == 9);    //Show x on screen   std::copy(x.begin(),x.end(),std::ostream_iterator<int>(std::cout," "));   std::cout << '\n'; }`
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

 

Screen output:

 

  -----------
  ` 1 4 9 `
  -----------

 

 

 

 

 





 

[![Valid XHTML 1.0 Strict](valid-xhtml10.png){width="88"
height="31"}](http://validator.w3.org/check?uri=referer)