project( panini )

cmake_minimum_required(VERSION 3.1)
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_BUILD_TYPE RelWithDebInfo)

add_definitions ( -Wall )

find_package (Qt5Widgets REQUIRED)
find_package (Qt5Core REQUIRED)
find_package (Qt5Gui REQUIRED)
find_package(Qt5OpenGL REQUIRED)
find_package(OpenGL REQUIRED)
find_package(ZLIB REQUIRED)

include_directories( ${OPENGL_INCLUDE_DIRS})

set ( panini_HDRS
	src/pvQt_QTVR.h
	src/panosurface.h
	src/panosphere.h
	src/panocylinder.h
	)

set ( panini_SRCS
	src/main.cpp
	src/pvQtPic.cpp
	src/pvQtView.cpp
	src/MainWindow.cpp
	src/GLwindow.cpp
	src/pvQt_QTVR.cpp
	src/picTypeDialog.cpp
	src/pictureTypes.cpp
	src/panosurface.cpp
	src/panosphere.cpp
	src/panocylinder.cpp
	src/TurnDialog.cpp
	src/About.cpp
	)

set ( panini_UIS
	ui/mainwindow.ui
	ui/picTypeDialog.ui
	ui/About.ui
	ui/ShowText.ui
	ui/TurnDialog.ui
	ui/CubeLimit_dialog.ui
	)
QT5_WRAP_UI(UIS ${panini_UIS})

set ( panini_RSCS
	ui/PaniniIcon.qrc
	)
QT5_ADD_RESOURCES(RSCS ${panini_RSCS})

set ( panini_MOCS
	src/pvQtPic.h
	src/CubeLimit_dialog.h
	src/pvQtView.h
	src/MainWindow.h
	src/GLwindow.h
	src/picTypeDialog.h
	src/About.h
	src/pvQtMouseModes.h
	src/TurnDialog.h
	)
QT5_WRAP_CPP(MOCS ${panini_MOCS})

add_executable ( panini ${panini_SRCS} ${UIS} ${RSCS} ${TRS} ${MOCS} )
target_link_libraries ( panini  Qt5::Core Qt5::Gui Qt5::Widgets Qt5::OpenGL ${OPENGL_LIBRARIES} ZLIB::ZLIB)
