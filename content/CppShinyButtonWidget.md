



 

 

 

 

 

([C++](Cpp.htm)) [ShinyButtonWidget](CppShinyButtonWidget.htm)
==============================================================

 

![STL](PicStl.png)![Qt
Creator](PicQtCreator.png)![Lubuntu](PicLubuntu.png)

 

[ShinyButtonWidget](CppShinyButtonWidget.htm) is a [class](CppClass.htm)
for a shiny button widget.

Technical facts
---------------

 

 

 

 

 

 

./CppShinyButtonWidget/CppShinyButtonWidget.pri
-----------------------------------------------

 

  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  ` INCLUDEPATH += \     ../../Classes/CppShinyButtonWidget  SOURCES += \     ../../Classes/CppShinyButtonWidget/shinybuttonwidget.cpp  HEADERS  += \     ../../Classes/CppShinyButtonWidget/shinybuttonwidget.h  OTHER_FILES += \     ../../Classes/CppShinyButtonWidget/Licence.txt`
  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

 

 

 

 

 

./CppShinyButtonWidget/shinybuttonwidget.h
------------------------------------------

 

  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  ` //--------------------------------------------------------------------------- /* ShinyButtonWidget, widget for the ShinyButton class Copyright (C) 2011-2015 Richel Bilderbeek  This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.  This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details. You should have received a copy of the GNU General Public License along with this program. If not, see <http://www.gnu.org/licenses/>. */ //--------------------------------------------------------------------------- //From http://www.richelbilderbeek.nl/CppShinyButtonWidget.htm //--------------------------------------------------------------------------- #ifndef SHINYBUTTONWIDGET_H #define SHINYBUTTONWIDGET_H  #pragma GCC diagnostic push #pragma GCC diagnostic ignored "-Weffc++" #pragma GCC diagnostic ignored "-Wunused-local-typedefs" #include <boost/scoped_ptr.hpp> #include <boost/signals2.hpp> #include "widget.h" #pragma GCC diagnostic pop  namespace ribi {  struct ShinyButton;  struct ShinyButtonWidget : public Widget {   explicit ShinyButtonWidget(     const double color,     const double gradient,     const std::string& text = "",     const Rect rect = CreateRect(0,0,80,20)   );   ShinyButtonWidget(const ShinyButtonWidget&) = delete;   ShinyButtonWidget& operator=(const ShinyButtonWidget&) = delete;   ~ShinyButtonWidget() noexcept {}          ShinyButton * GetShinyButton()       noexcept { return m_button.get(); }   const ShinyButton * GetShinyButton() const noexcept { return m_button.get(); }    void Click() noexcept;   static std::string GetVersion() noexcept;   static std::vector<std::string> GetVersionHistory() noexcept;    ///The signal emitted when the ShinyButtonWidget is clicked   mutable boost::signals2::signal<void (const ShinyButtonWidget* const)> m_signal_clicked;    private:    ///The ShinyButton   boost::scoped_ptr<ShinyButton> m_button;    ///Allow std::cout access to ShinyButtonWidget   friend std::ostream& operator<<(std::ostream& os, const ShinyButtonWidget& button) noexcept; };  std::ostream& operator<<(std::ostream& os, const ShinyButtonWidget& button) noexcept;  } //~namespace ribi  #endif // SHINYBUTTONWIDGET_H`
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

 

 

 

 

 

./CppShinyButtonWidget/shinybuttonwidget.cpp
--------------------------------------------

 

  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  ` //--------------------------------------------------------------------------- /* ShinyButtonWidget, widget for the ShinyButton class Copyright (C) 2011-2015 Richel Bilderbeek  This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.  This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details. You should have received a copy of the GNU General Public License along with this program. If not, see <http://www.gnu.org/licenses/>. */ //--------------------------------------------------------------------------- //From http://www.richelbilderbeek.nl/CppShinyButtonWidget.htm //--------------------------------------------------------------------------- #pragma GCC diagnostic push #pragma GCC diagnostic ignored "-Weffc++" #pragma GCC diagnostic ignored "-Wunused-local-typedefs" #include "shinybuttonwidget.h"  #include <cassert> #include <cmath>  #include "shinybutton.h" #include "trace.h"  #pragma GCC diagnostic pop  ribi::ShinyButtonWidget::ShinyButtonWidget(   const double color,   const double gradient,   const std::string& text,   const Rect rect)   : m_signal_clicked{},     m_button(new ShinyButton(color,gradient,text)) {   this->SetGeometry(rect); }  void ribi::ShinyButtonWidget::Click() noexcept {   m_signal_clicked(this); }  std::string ribi::ShinyButtonWidget::GetVersion() noexcept {   return "1.2"; }  std::vector<std::string> ribi::ShinyButtonWidget::GetVersionHistory() noexcept {   return {     "2011-09-21: version 1.0: initial version",     "2011-10-29: version 1.1: added Click member function and m_signal_clicked",     "2014-03-28: version 1.2: replaced Rect by Boost.Geometry its box class"   }; }  std::ostream& ribi::operator<<(std::ostream& os, const ShinyButtonWidget& button) noexcept {   os     << "<ShinyButtonWidget>"     << *button.m_button     //<< button.GetGeometry()     << "</ShinyButtonWidget>";   return os; }`
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

 

 

 

 

 





 

[![Valid XHTML 1.0 Strict](valid-xhtml10.png){width="88"
height="31"}](http://validator.w3.org/check?uri=referer)

This page has been created by the [tool](Tools.htm)
[CodeToHtml](ToolCodeToHtml.htm)