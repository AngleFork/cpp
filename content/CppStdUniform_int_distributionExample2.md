



 

 

 

 

 

([C++](Cpp.htm)) [StdUniform\_int\_distributionExample2](CppStdUniform_int_distributionExample2.htm)
====================================================================================================

 

Technical facts
---------------

 

[Operating system(s) or programming environment(s)](CppOs.htm)

-   ![Lubuntu](PicLubuntu.png) [Lubuntu](CppLubuntu.htm) 15.04 (vivid)

[IDE(s)](CppIde.htm):

-   ![Qt Creator](PicQtCreator.png) [Qt Creator](CppQtCreator.htm) 3.1.1

[Project type](CppQtProjectType.htm):

-   ![console](PicConsole.png) [Console
    application](CppConsoleApplication.htm)

[C++ standard](CppStandard.htm):

-   ![C++98](PicCpp98.png) [C++98](Cpp98.htm)

[Compiler(s)](CppCompiler.htm):

-   [G++](CppGpp.htm) 4.9.2

[Libraries](CppLibrary.htm) used:

-   ![STL](PicStl.png) [STL](CppStl.htm): GNU ISO C++ Library, version
    4.9.2

 

 

 

 

 

[Qt project file](CppQtProjectFile.htm): ./CppStdUniform\_int\_distributionExample2/CppStdUniform\_int\_distributionExample2.pro
--------------------------------------------------------------------------------------------------------------------------------

 

  -----------------------------------------------------------------
  ` include("../../ConsoleApplication.pri")  SOURCES += main.cpp`
  -----------------------------------------------------------------

 

 

 

 

 

./CppStdUniform\_int\_distributionExample2/main.cpp
---------------------------------------------------

 

  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  ` #include <iostream> #include <random>  int main() {   std::random_device rd;    //Use a random seed   std::mt19937 rng(rd());    //Draw random numbers from 0 to and including 123   std::uniform_int_distribution<int> distribution(0,123);    for (int i=0; i!=10; ++i)   {     std::cout << distribution(rng) << '\n';   } }`
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

 

 

 

 

 





 

[![Valid XHTML 1.0 Strict](valid-xhtml10.png){width="88"
height="31"}](http://validator.w3.org/check?uri=referer)

This page has been created by the [tool](Tools.htm)
[CodeToHtml](ToolCodeToHtml.htm)