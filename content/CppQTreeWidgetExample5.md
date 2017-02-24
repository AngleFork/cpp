



 

 

 

 

 

([C++](Cpp.htm)) ![Qt](PicQt.png) [QTreeWidgetExample5](CppQTreeWidgetExample5.htm)
===================================================================================

 

[QTreeWidgetExample5](CppQTreeWidgetExample5.htm) is an example of
[QTreeWidgetExample5](CppQTreeWidgetExample5.htm).

 

-   [Download the Qt Creator project
    'CppQTreeWidgetExample5' (zip)](CppQTreeWidgetExample5.zip)

 

 

 

 

 

Technical facts
---------------

 

[Application type(s)](CppApplication.htm)

-   ![Desktop](PicDesktop.png) [Desktop
    application](CppDesktopApplication.htm)

[Operating system(s) or programming environment(s)](CppOs.htm)

-   ![Lubuntu](PicLubuntu.png) [Lubuntu](CppLubuntu.htm) 12.10 (quantal)

[IDE(s)](CppIde.htm):

-   ![Qt Creator](PicQtCreator.png) [Qt Creator](CppQtCreator.htm) 2.5.2

[Project type](CppQtProjectType.htm):

-   ![GUI](PicGui.png) [GUI application](CppGuiApplication.htm)

[C++ standard](CppStandard.htm):

-   ![C++98](PicCpp98.png) [C++98](Cpp98.htm)

[Compiler(s)](CppCompiler.htm):

-   [G++](CppGpp.htm) 4.7.2

[Libraries](CppLibrary.htm) used:

-   ![Qt](PicQt.png) [Qt](CppQt.htm): version 4.8.3 (32 bit)
-   ![STL](PicStl.png) [STL](CppStl.htm): GNU ISO C++ Library, version
    4.7.2

 

 

 

 

 

[Qt project file](CppQtProjectFile.htm): CppQTreeWidgetExample5.pro
-------------------------------------------------------------------

 

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------
  ` QT       += core gui greaterThan(QT_MAJOR_VERSION, 4): QT += widgets TARGET = CppQTreeWidgetExample5 TEMPLATE = app SOURCES += main.cpp HEADERS  += FORMS    += `
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------

 

 

 

 

 

main.cpp
--------

 

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  ` #include <cassert> #include <QApplication> #include <QDebug> #include <QDropEvent> #include <QTreeWidget> #include <QTreeWidgetItem> #include <QDesktopWidget>  struct TwoLevelsDeepTree : public QTreeWidget {   explicit TwoLevelsDeepTree(QWidget *parent = 0)     : QTreeWidget(0)   {     //Hide the header     setHeaderHidden(true);      //Add ten regular items     for (int i=0; i!=10; ++i)     {         QTreeWidgetItem * const item = new QTreeWidgetItem;         item->setText(0,"Item #" + QString::number(i+1));         //Allow the item to be edited         item->setFlags( item->flags() | Qt::ItemIsEditable);         addTopLevelItem(item);     }      //Let the row colors alternate     setAlternatingRowColors(true);      //Allow items to be drag and dropped inside of the widget     setDragDropMode(QAbstractItemView::InternalMove);      //Let the drag and drop be animated     setAnimated(true);    }   protected:   void dropEvent(QDropEvent *event)   {     QTreeWidget::dropEvent(event);     //Fix the possibility of dropping a tree with depth three     while (1)     {       bool done = true;       const int n_top = this->topLevelItemCount();       for (int i=0; i!=n_top; ++i)       {         assert(i < this->topLevelItemCount());         QTreeWidgetItem * const top = this->topLevelItem(i);         const int n_child = top->childCount();         for (int j=0; j!=n_child; ++j)         {           assert(j < top->childCount());           //Check if top->child(j) has children           if (top->child(j)->childCount() > 0)           {             //Move top->child(j) to top             QTreeWidgetItem * const clone = top->child(j)->clone();             this->addTopLevelItem(clone);             //this->insertTopLevelItem(this->indexFromItem(             top->removeChild(top->child(j));             done = false;             j = n_child - 1;             i = n_top - 1;           }         }       }       //End the while loop if no parents were moved       if (done) break;     }     #ifndef NDEBUG     //Check that there are no items at depth three     {       const int n_top = this->topLevelItemCount();       for (int i=0; i!=n_top; ++i)       {         QTreeWidgetItem * const top = this->topLevelItem(i);         const int n_child = top->childCount();         for (int j=0; j!=n_child; ++j)         {           if (top->child(j)->childCount() > 0)           {             assert(!"Should not find a child with a child");           }         }       }     }     #endif     //Process all items     {       const int n_top = this->topLevelItemCount();       for (int i=0; i!=n_top; ++i)       {         QTreeWidgetItem * const top = this->topLevelItem(i);          //Let all top items auto-expand          top->setExpanded(true);         //Allow dropping on top-level items         top->setFlags(               Qt::ItemIsSelectable             | Qt::ItemIsEnabled             | Qt::ItemIsEditable             | Qt::ItemIsDragEnabled             | Qt::ItemIsDropEnabled);         assert(GetDepth(top)==0);         const int n_child = top->childCount();         for (int j=0; j!=n_child; ++j)         {             assert(GetDepth(top->child(j))==1);             //Disallow dropping on non-top-level items             top->child(j)->setFlags(                   Qt::ItemIsSelectable               | Qt::ItemIsEnabled               | Qt::ItemIsEditable               | Qt::ItemIsDragEnabled);         }       }     }   }   private:   ///Find out the depth of an item   int GetDepth(const QTreeWidgetItem * const item)   {     assert(item);     int depth = 0;     const QTreeWidgetItem * copy = item->parent();     while(copy)     {       ++depth;       copy = copy->parent();     }     return depth;   } };  int main(int argc, char *argv[]) {   QApplication a(argc, argv);   TwoLevelsDeepTree w;     w.show();    //Put the QTreeWidget in the center of the screen at 25% of the screen its size   {     const QRect screen = QApplication::desktop()->screenGeometry();     w.setGeometry(0,0,screen.width() * 1 / 4 ,screen.height() * 1 / 2);     w.move( screen.center() - w.rect().center() );   }   return a.exec(); } `
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

 

 

 

 

 





 

[![Valid XHTML 1.0 Strict](valid-xhtml10.png){width="88"
height="31"}](http://validator.w3.org/check?uri=referer)

This page has been created by the [tool](Tools.htm)
[CodeToHtml](ToolCodeToHtml.htm)