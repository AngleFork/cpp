



 

 

 

 

 

([C++](Cpp.htm)) [CLK\_TCK was not declared in this scope](CppCompileErrorCLK_TCKwasNotDeclaredInThisScope.htm)
===============================================================================================================

 

[Compile error](CppCompileError.htm) that might occur when using my
[Gnuplot Interface](CppGnuplotInterface.htm) [class](CppClass.htm).

 

I found this definition in the header file 'time.h'. If you cannot find
it, use the code below instead.

 

  -----------------------------------
  ` const double CLK_TCK = 1000.0;`
  -----------------------------------

 

 

 

 

 





 

[![Valid XHTML 1.0 Strict](valid-xhtml10.png){width="88"
height="31"}](http://validator.w3.org/check?uri=referer)

This page has been created by the [tool](Tools.htm)
[CodeToHtml](ToolCodeToHtml.htm)