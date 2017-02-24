



 

 

 

 

 

([C++](Cpp.htm)) [Unable to open file 'UNITFORM\_MYFORM.OBJ'](CppLinkErrorUnableToOpenFormObj.htm)
==================================================================================================

 

[Link error](CppLinkError.htm).

 

IDE: [C++ Builder](CppBuilder.htm) 6.0

Project type: [VCL](CppVcl.htm)

 

 

 

 

 

Full error messages
-------------------

 

  --------------------------------------------------------------------------
  ` [Linker Fatal Error] Fatal: Unable to open file 'UNITFORM_MYFORM.OBJ'`
  --------------------------------------------------------------------------

 

 

 

 

 

Cause
-----

 

Due to a Rename refactoring the following \#pragma was renamed from

 

  ----------------------------------
  ` #pragma link "UnitFormMyForm"`
  ----------------------------------

 

to

 

  -----------------------------------
  ` #pragma link "UnitForm_MyForm"`
  -----------------------------------

 

But the filename for this Form remained UnitFormMyForm. Therefore,
UnitForm\_MyForm.obj could not be found.

 

 

 

 

 

Solution
--------

 

Let the \#pragma link to an existing Form:

 

  ----------------------------------
  ` #pragma link "UnitFormMyForm"`
  ----------------------------------

 

 

 

 

 





 

[![Valid XHTML 1.0 Strict](valid-xhtml10.png){width="88"
height="31"}](http://validator.w3.org/check?uri=referer)