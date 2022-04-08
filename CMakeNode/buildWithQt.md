# 设置find_package的查找目录
set(CMAKE_PREFIX_PATH "C:/Qt/Qt5.9.0/5.9.0/msvc2015_64")

# 自动进行moc宏解析
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

# 使用find_package定位Qt的头文件和库文件的位置
find_package(Qt5 COMPONENTS
  Core
  Gui
  Widgets
  REQUIRED)
  
# 生成exe文件
add_executable(my_exe main.cpp)  
  
# 链接
target_link_libraries(my_exe
  Qt5::Core
  Qt5::Gui
  Qt5::Widgets
)
