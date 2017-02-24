



 

 

 

 

 

([C++](Cpp.htm)) [\[...\]\\NAME.LIB contains invalid OMF record, type 0x21 (possibly COFF)](CppLinkErrorLibContainsInvalidOmfRecord.htm)
========================================================================================================================================

 

[Link error](CppLinkError.htm).

 

[IDE](CppIde.htm): [C++ Builder](CppBuilder.htm) 6.0

Project type: [VCL](CppVcl.htm)

 

 

 

 

 

Full error message
------------------

 

  -----------------------------------------------------------------------------------------
  ` [Linker Error] [...]\NAME.LIB contains invalid OMF record, type 0x21 (possibly COFF)`
  -----------------------------------------------------------------------------------------

 

 

 

 

 

Cause
-----

 

The library is of the wrong type. Use coff2omf.exe, located in the
CBuilder/bin folder, to convert it to the correct type.

 

 

 

 

 

Solution
--------

 

The following MS-DOS commands converts a COFF library called MyLib.lib
to the OMF library file MyNewLib.lib, after making a backup file called
MyBackupLib.lib:

 

  -----------------------------------------------------------------------------------------------
  ` copy MyLib.lib MyBackupLib.lib coff2omf MyLib.lib MyNewLib.lib copy MyNewLib.lib MyLib.lib`
  -----------------------------------------------------------------------------------------------

 

 

 

 

 





 

[![Valid XHTML 1.0 Strict](valid-xhtml10.png){width="88"
height="31"}](http://validator.w3.org/check?uri=referer)