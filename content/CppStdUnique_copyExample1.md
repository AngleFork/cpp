



 

 

 

 

 

([C++](Cpp.htm)) [StdUnique\_copyExample1](CppStdUnique_copyExample1.htm)
=========================================================================

 

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

 

 

 

 

 

[Qt project file](CppQtProjectFile.htm): ./CppStdUnique\_copyExample1/CppStdUnique\_copyExample1.pro
----------------------------------------------------------------------------------------------------

 

  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  ` include(../../ConsoleApplication.pri) #Or use the code below # QT += core # QT += gui # greaterThan(QT_MAJOR_VERSION, 4): QT += widgets # CONFIG   += console # CONFIG   -= app_bundle # TEMPLATE = app # CONFIG(release, debug|release) { #   DEFINES += NDEBUG NTRACE_BILDERBIKKEL # } # QMAKE_CXXFLAGS += -std=c++11 -Wall -Wextra -Weffc++ # unix { #   QMAKE_CXXFLAGS += -Werror # }  include(../../Libraries/Boost.pri) #Or use the code below # win32 { #   INCLUDEPATH += \ #     ../../Libraries/boost_1_54_0 # }  SOURCES += main.cpp`
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

 

 

 

 

 

./CppStdUnique\_copyExample1/main.cpp
-------------------------------------

 

  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  ` #include <cassert> #include <algorithm> #include <vector>  int main() {   std::vector<int> v;   v.push_back(0);   v.push_back(1);   v.push_back(1);   v.push_back(2);   v.push_back(2);   v.push_back(2);   v.push_back(3);   v.push_back(3);   v.push_back(3);   v.push_back(3);   std::vector<int> w;   std::unique_copy(v.begin(),v.end(),std::back_inserter(w));   assert(w[0]==0);   assert(w[1]==1);   assert(w[2]==2);   assert(w[3]==3); }`
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

 

 

 

 

 





 

[![Valid XHTML 1.0 Strict](valid-xhtml10.png){width="88"
height="31"}](http://validator.w3.org/check?uri=referer)

This page has been created by the [tool](Tools.htm)
[CodeToHtml](ToolCodeToHtml.htm)