Potentially useful stuff for Chapter 6 of PySideSummer repository: https://github.com/EricThomson/PySideSummer


#Useful links

#Useful documentation
##QtGui.QMainWindow
http://srinikom.github.io/pyside-docs/PySide/QtGui/QMainWindow.html
    A main window provides a framework for building an application�s user interface. Qt has PySide.QtGui.QMainWindow and its related classes for main window management. PySide.QtGui.QMainWindow has its own layout to which you can add PySide.QtGui.QToolBars, PySide.QtGui.QDockWidgets, a PySide.QtGui.QMenuBar, and a PySide.QtGui.QStatusBar. 
    The layout has a center area that can be occupied by any kind of widget. 
    
    A central widget will typically be a standard Qt widget such as a PySide.QtGui.QTextEdit or a PySide.QtGui.QGraphicsView . Custom widgets can also be used for advanced applications. You set the central widget with setCentralWidget(). 
    Main windows have either a single (SDI) or multiple (MDI) document interface. You create MDI applications in Qt by using a PySide.QtGui.QMdiArea as the central widget. Note: Creating a main window without a central widget is not supported. You must have a central widget even if it is just a placeholder.

    ###Menubars and toolbars
    	Qt implements menus in PySide.QtGui.QMenu and PySide.QtGui.QMainWindow
    keeps them in a PySide.QtGui.QMenuBar . PySide.QtGui.QAction s are added to the 
    menus, which display them as menu items. You can add new menus to the main window�s 
    menu bar by calling menuBar() , which returns the PySide.QtGui.QMenuBar for the 
    window, and then add a menu with QMenuBar.addMenu().
    
    Similarly, toolbars are implemented in the PySide.QtGui.QToolBar class. You add 
    a toolbar to a main window with addToolBar().


    ###Dock Widgets
        Dock widgets are implemented in the PySide.QtGui.QDockWidget class. A dock 
    widget is a window that can be docked into the main window. You add dock widgets 
    to a main window with addDockWidget() .
    
    There are four dock widget areas as given by the Qt.DockWidgetArea enum: left, right, 
    top, and bottom. You can specify which dock widget area that should occupy the corners 
    where the areas overlap with setCorner() . By default each area can only contain one 
    row (vertical or horizontal) of dock widgets, but if you enable nesting with 
    setDockNestingEnabled() , dock widgets can be added in either direction.
    
    While only one widget can be added to a dock widget (note it can be very 
    complicated, so this isn't a real limitation), two dock widgets may also be 
    stacked on top of each other. A PySide.QtGui.QTabBar is then used to select which 
    of the widgets that should be displayed.


##QStatus Bar 
http://srinikom.github.io/pyside-docs/PySide/QtGui/QStatusBar.html

    The PySide.QtGui.QStatusBar class provides a horizontal bar suitable for 
    presenting status information. You can set a status bar with setStatusBar() , 
    but one is created the first time statusBar() (which returns the main window�s 
    status bar) is called. 

    Typically, a request for the status bar functionality occurs in relation to a 
    PySide.QtGui.QMainWindow object. PySide.QtGui.QMainWindow provides a main 
    application window, with a menu bar, tool bars, dock widgets and a status bar 
    around a large central widget. The status bar can be retrieved using the 
    QMainWindow.statusBar() function, and replaced using the QMainWindow.setStatusBar() 
    function.

    To remove a temporary message, use the PySide.QtGui.QStatusBar.clearMessage() 
    slot, or set a time limit when calling PySide.QtGui.QStatusBar.showMessage().


##QtCore.QSettings*
srinikom.github.io/pyside-docs/PySide/QtCore/QSettings.html

    The PySide.QtCore.QSettings class provides persistent platform-independent 
    application settings. Users normally expect an application to remember its 
    settings (window sizes and positions, options, etc.) across sessions. This 
    information is often stored in the system registry on Windows, and in XML 
    preferences files on Mac OS X. PySide.QtCore.QSettings is an abstraction around 
    these technologies, enabling you to save and restore application settings in 
    a portable manner.
    
    PySide.QtCore.QSettings stores settings. Each setting consists of 
    a PySide.QtCore.QString that specifies the setting�s name (the key ) 
    and a PySide.QtCore.QVariant that stores the data associated with 
    the key. To write a setting, use PySide.QtCore.QSettings.setValue(). 
    For example:
    
    	settings.setValue("editor/wrapMargin", 68)
    
    If there already exists a setting with the same key, the existing 
    value is overwritten by the new value. 
    
    You can get a setting�s value back using PySide.QtCore.QSettings.value() :
    
    	margin = int(settings.value("editor/wrapMargin"))
    
    If there is no setting with the specified name, PySide.QtCore.QSettings 
    returns a null PySide.QtCore.QVariant (which can be converted to the 
    integer 0). You can specify another default value by passing 
    a second argument to PySide.QtCore.QSettings.value() :
    
    	margin = int(settings.value("editor/wrapMargin", 80))
    
    To test whether a given key exists, call PySide.QtCore.QSettings.contains(). 
    To remove the setting associated with a key, call PySide.QtCore.QSettings.remove() . 
    To obtain the list of all keys, call PySide.QtCore.QSettings.allKeys() . 
    To remove all keys, call PySide.QtCore.QSettings.clear() .       
            
        
##QtCore.QFile
http://srinikom.github.io/pyside-docs/PySide/QtCore/QFile.html
    The PySide.QtCore.QFile class provides an interface for reading from and writing to files.
    
    PySide.QtCore.QFile is an I/O device for reading and writing text and binary files and 
    resources . A PySide.QtCore.QFile may be used by itself or, more conveniently, with 
    a PySide.QtCore.QTextStream or PySide.QtCore.QDataStream .
    
    The file name is usually passed in the constructor, but it can be set at any time 
    using PySide.QtCore.QFile.setFileName() . PySide.QtCore.QFile expects the file 
    separator to be �/� regardless of operating system. The use of other separators 
    (e.g., ��) is not supported.
    
    You can check for a file�s existence using PySide.QtCore.QFile.exists(). Remove a file 
    using PySide.QtCore.QFile.remove(). The file is opened with 
    PySide.QtCore.QFile.open(), closed with PySide.QtCore.QFile.close(), 
    and flushed with PySide.QtCore.QFile.flush(). 
    
    The size of the file is returned by PySide.QtCore.QFile.size().  
    

##QFileDialog
http://srinikom.github.io/pyside-docs/PySide/QtGui/QFileDialog.html

    The PySide.QtGui.QFileDialog class provides a dialog that allow users to select files 
    or directories. It enables a user to traverse the file system in order to select one 
    or many files or a directory.
    
    In the following example, a modal QFileDialog is created using a static function. 
    The dialog initially displays the contents of the �/home/jana� directory, and displays 
    files matching the patterns given in the string �Image Files (*.png *.jpg *.bmp)�. 
    The parent of the file dialog is set to self , and the window title is set to �Open Image�:
         fileName = QFileDialog.getOpenFileName(self,
            tr("Open Image"), "/home/jana", tr("Image Files (*.png *.jpg *.bmp)"))
    Note using getOpenFileName returns the file path in a tuple that also includes the file 
    type list, so you can append [0] if you just want the file path.


##QPixMap
http://srinikom.github.io/pyside-docs/PySide/QtGui/QPixmap.html
    There are functions to convert between PySide.QtGui.QImage and PySide.QtGui.QPixmap . 
    Typically, the PySide.QtGui.QImage class is used to load an image file, optionally 
    manipulating the image data, before the PySide.QtGui.QImage object is converted into 
    a PySide.QtGui.QPixmap to be shown on screen. Alternatively, if no manipulation is 
    desired, the image file can be loaded directly into a PySide.QtGui.QPixmap . 
    
    PySide.QtGui.QPixmap provides a collection of functions that can be used to obtain 
    a variety of information about the pixmap. In addition, there are several functions 
    that enables transformation of the pixmap.


##QImage
http://srinikom.github.io/pyside-docs/PySide/QtGui/QImage.html
    The PySide.QtGui.QImage class provides a hardware-independent image representation 
    that allows direct access to the pixel data, and can be used as a paint device.
    
    Qt provides four classes for handling image data: PySide.QtGui.QImage , PySide.QtGui.QPixmap, 
    PySide.QtGui.QBitmap and PySide.QtGui.QPicture . PySide.QtGui.QImage is designed and 
    optimized for I/O, and for direct pixel access and manipulation, while PySide.QtGui.QPixmap 
    is designed and optimized for showing images on screen. 
    
    The PySide.QtGui.QImage class supports several image formats described by the QImage.Format enum.
    
    PySide.QtGui.QImage provides a collection of functions that can be used to obtain 
    a variety of information about the image. There are also several functions that enables 
    transformation of the image.
    
    PySide.QtGui.QImage provides several ways of loading an image file: The file can be 
    loaded when constructing the PySide.QtGui.QImage object, or by using the PySide.QtGui.QImage.load() 
    or PySide.QtGui.QImage.loadFromData() functions later on. The complete list of supported 
    file formats are available through the QImageReader.supportedImageFormats() and 
    QImageWriter.supportedImageFormats() functions
    
    Simply call the PySide.QtGui.QImage.save() function to save a PySide.QtGui.QImage object.


##QtGui.QPrinter
http://srinikom.github.io/pyside-docs/PySide/QtGui/QPrinter.html
    The PySide.QtGui.QPrinter class is a paint device that paints on a printer.
    When printing directly to a printer on Windows or Mac OS X, PySide.QtGui.QPrinter 
    uses the built-in printer drivers.
    
    This device represents a series of pages of printed output, and is used in almost 
    exactly the same way as other paint devices such as PySide.QtGui.QWidget and 
    PySide.QtGui.QPixmap . A set of additional functions are provided to manage 
    device-specific features, such as orientation and resolution, and to step through 
    the pages in a document as it is generated.