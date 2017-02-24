



 

 

 

 

 

([C++](Cpp.htm)) [GetRootBranches](CppGetRootBranches.htm)
==========================================================

 

[GetRootBranches](CppGetRootBranches.htm) is a [Newick](CppNewick.htm)
[code snippet](CppCodeSnippets.htm) to obtain the
[Newick](CppNewick.htm)'s two root branches: from the
[Newick](CppNewick.htm) '(X,Y)' (where both X and Y might be complex),
it returns 'X' and 'Y'.

 

  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  ` ///GetRootBranches obtains the two root branches from a binary Newick. ///Examples: ///    (1,2)     ->     {1 , 2} ///    (1,(2,3)) ->     {1 , (2,3)} ///((1,2),(3,4)) -> {(1,2) , (3,4)} ///From http://www.richelbilderbeek.nl/CppGetRootBranches.htm const std::pair<std::vector<int>,std::vector<int> >   GetRootBranches(const std::vector<int>& n) {   assert(IsNewick(n));   assert(IsBinaryNewick(n));   assert(n.size() > 3     && "A Newick must have at least two values");   assert(n[0] == BinaryNewickVector::bracket_open);   assert(n[n.size()-1] == BinaryNewickVector::bracket_close);   const int sz = boost::numeric_cast<int>(n.size());   //Return the answer directly is Newick consists   //out of two values only   if (sz==4)   {     assert(n[1] > 0);     assert(n[2] > 0);     return std::make_pair(       CreateVector(         static_cast<int>(BinaryNewickVector::bracket_open),         n[1],         static_cast<int>(BinaryNewickVector::bracket_close)),       CreateVector(         static_cast<int>(BinaryNewickVector::bracket_open),         n[2],         static_cast<int>(BinaryNewickVector::bracket_close)));   }   //Check the kind of Newick   //1) (x(yz))    return {    x,(yz) }   //2) ((xy)z)    return { (xy), (z) }   //3) ((ab)(cd)) return { (ab),(cd) }   if (n[1]>0)   {     //1) (x(yz))    return {    x,(yz) }     return std::make_pair(       CreateVector(         static_cast<int>(BinaryNewickVector::bracket_open)         ,n[1],         static_cast<int>(BinaryNewickVector::bracket_close)),       std::vector<int>(n.begin()+2,n.end()-1));   }   else if (n[n.size()-2]>0)   {     //2) ((xy)z)    return { (xy), (z) }     return std::make_pair(       std::vector<int>(n.begin()+1,n.end()-2),       CreateVector(         static_cast<int>(BinaryNewickVector::bracket_open),         n[sz-2],         static_cast<int>(BinaryNewickVector::bracket_close)));   }   else   {     //3) ((ab)(cd)) return { (ab),(cd) }     //Find ')('     int i = 0;     for (; i!=sz-1; ++i)     {       if ( n[i  ]==BinaryNewickVector::bracket_close         && n[i+1]==BinaryNewickVector::bracket_open)       break;     }     assert(i!=sz-1 && "Sequence )( must be found");     return std::make_pair(       std::vector<int>(n.begin()+1,n.begin()+i+1),       std::vector<int>(n.begin()+i+1,n.end()-1));   } }`
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

 

 

 

 

 





 

[![Valid XHTML 1.0 Strict](valid-xhtml10.png){width="88"
height="31"}](http://validator.w3.org/check?uri=referer)