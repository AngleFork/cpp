



 

 

 

 

 

([C++](Cpp.htm)) [ContainerToStr](CppContainerToStr.htm)
========================================================

 

[ContainerToStr](CppContainerToStr.htm) is a
[container](CppContainer.htm) and [convert](CppConvert.htm) [code
snippet](CppCodeSnippets.htm) to [convert](CppConvert.htm) a
[container](CppContainer.htm) to [std::string](CppString.htm).

 

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  ` #include <sstream>  template <class Container> const std::string ContainerToStr(const Container& c, const std::string& seperator = " ") {   std::stringstream s;   std::copy(c.begin(),c.end(),     std::ostream_iterator<typename Container::value_type>(s,seperator.c_str()));   return s.str(); }`
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

 

 

 

 

 





 

[![Valid XHTML 1.0 Strict](valid-xhtml10.png){width="88"
height="31"}](http://validator.w3.org/check?uri=referer)