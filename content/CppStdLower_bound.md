
 

 

 

 

 

([C++](Cpp.md)) [std::lower\_bound](CppStdLower_bound.md)
========================================================

 

[std::lower\_bound](CppStdLower_bound.md) is an [STL](CppStl.md)
[algorithm](CppAlgorithm.md) to find an element in a
[container](CppContainer.md) smaller than a certain value.

 

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  ` #include <algorithm> #include <cassert> #include <vector>  int main() {   std::vector<int> v;   v.push_back(1);   v.push_back(2);   v.push_back(3);    //Lower bound will point to first element not smaller than 2   assert(*std::lower_bound(v.begin(),v.end(),2)==2);    //Upper bound will point to first element larger than 2   assert(*std::upper_bound(v.begin(),v.end(),2)==3); } `
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

 

 

 

 

 

 

