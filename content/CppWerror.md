



 

 

 

 

 

([C++](Cpp.htm)) [-Werror](CppWerror.htm)
=========================================

 

When adding [-Werror](CppWerror.htm) to a [Qt Creator](CppQtCreator.htm)
[project file](CppQtProjectFile.htm) like below, [compile
warnings](CppCompileWarning.htm) will be treated like [compile
errors](CppCompileError.htm).

 

  ------------------------------
  ` QMAKE_CXXFLAGS += -Werror`
  ------------------------------

 

[Compile](CppCompiler.htm) cleanly at high warning levels \[1\]. Prefer
[compile errors](CppCompileError.htm) to [runtime
errors](CppRuntimeError.htm) \[2\].

 

 

 

 

 

[References](CppReferences.htm)
-------------------------------

 

1.  [Herb Sutter](CppHerbSutter.htm), [Andrei
    Alexandrescu](CppAndreiAlexandrescu.htm). C++ coding standards: 101
    rules, guidelines, and best practices. 2005. ISBN: 0-32-111358-6.
    Item 1: 'Compile cleanly at high warning levels'.
2.  [Herb Sutter](CppHerbSutter.htm), [Andrei
    Alexandrescu](CppAndreiAlexandrescu.htm). C++ coding standards: 101
    rules, guidelines, and best practices. ISBN: 0-32-111358-6. Item 14:
    'Prefer compile- and link-time errors to run-time errors'.

 

 

 

 

 





 

[![Valid XHTML 1.0 Strict](valid-xhtml10.png){width="88"
height="31"}](http://validator.w3.org/check?uri=referer)