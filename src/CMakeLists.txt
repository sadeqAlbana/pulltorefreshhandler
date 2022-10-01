cmake_minimum_required(VERSION 3.16)

find_package(QT NAMES Qt6 Qt5 REQUIRED COMPONENTS Core)
find_package(Qt${QT_VERSION_MAJOR} REQUIRED COMPONENTS Core)


qt_add_library(pulltorefreshhandler STATIC)
qt_add_qml_module(pulltorefreshhandler
    URI "com.melije.pulltorefresh"
    VERSION 1.0
    QML_FILES
        RefreshIndicator.qml
        PullToRefreshHandler.qml)

target_link_libraries(pulltorefreshhandler PRIVATE Qt${QT_VERSION_MAJOR}::Quick)
