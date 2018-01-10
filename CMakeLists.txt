cmake_minimum_required(VERSION 2.8)
PROJECT(CryptobugCoin)

FIND_PACKAGE(Qt4 REQUIRED)
INCLUDE(${QT_USE_FILE})
ADD_DEFINITIONS(${QT_DEFINITIONS})

SET(CryptobugCoin_SOURCES main.cpp MainWindow.cpp)
SET(CryptobugCoin_FORMS MainWindow.ui)
SET(CryptobugCoin_HEADERS MainWindow.h)

QT4_WRAP_CPP(CryptobugCoin_HEADERS_MOC ${CryptobugCoin_HEADERS})
QT4_WRAP_UI(CryptobugCoin_FORMS_HEADERS ${CryptobugCoin_FORMS})

INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR} ${CMAKE_CURRENT_BINARY_DIR})
ADD_EXECUTABLE(CryptobugCoin
    ${CryptobugCoin_SOURCES}
    ${CryptobugCoin_HEADERS_MOC}
    ${CryptobugCoin_FORMS_HEADERS}
)
TARGET_LINK_LIBRARIES(CryptobugCoin ${QT_LIBRARIES})