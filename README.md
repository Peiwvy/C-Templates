# C++编程模版
    
在以往的涉及到ROS的项目开发中，有一些通用问题阻碍了C++开发与调试工作的有序进行。我们希望构建一个标准化C++工程模块，模块化开发，辅以规范，以提高工作效率和代码质量，降低项目工期。

## Main Features

### 核心思想:
+ 对项目进行模块化设计，对算法模块进行封装；
+ 完成功能与ROS部分的解耦；
+ 完成业务与算法的解耦
+ 执行多种规范，包括代码命名规范、格式规范、文档规范以及版本管理规范
+ 使用现代C++工具，包括

### 功能架构


 + 模块层-modules：包含可复用的功能子模块，以及公共算法库common
 + 业务层-app：实现业务流程，将各modules拼接起来以实现最终功能
 + 通信层-ros：利用ros实现数据订阅、发布的封装
 ![image](https://sjtu.feishu.cn/space/api/box/stream/download/asynccode/?code=NzliZmQyNjgxZTNiNTNiODIyYTc2ZWMyYWU0NjYyYjNfUlZ0eXZkWUM0VXlvckhqWUxyMkt2YlRweWUzSWQ0dGFfVG9rZW46Ym94Y252UWFybFhNMXhxb0JydU9xZWRGVkplXzE2NzA0NzczOTc6MTY3MDQ4MDk5N19WNA)
### 代码规范
+ 命名规范：Google style  (文件、变量、函数、命名空间…)
+ 代码格式化：Clang-format、CMake-format
+ 静态检查：Clang-tidy
+ 单元测试：Gtest
+ 注释编写、文档生成：Doxygen
+ 版本管理：Git
### 开发工具
+ 编辑器: VisualStudio Code
+ 开发环境：Docker + DevContainer 插件
+ 代码Debug: CMake Tools插件 + gdb
+ common tool (公共工具类)
    + datatype: 自定义数据类型
    + logger: 基于glog的日志系统
    + configs: yaml参数文件读取  
    + benchmark: 运行时间、性能分析


## Prerequisite
+ OS：Ubuntu18.04
+ Editor：VisualStudio Code
+ Editor Add-ons: 
    + DevContainer
    + CMake  Tools；
    + Doxygen  Documentation Generator
+ Packages:
    + ROS Melodic
    + GCC >=7.5
    + CMake >=3.10.2
    + Doxygen
    + Docker
## Usage

### Docker
+ 本项目提供Docker环境，支持开箱即用
+ 需要先进行环境配置，详见[VSCode Docker开发环境配置](https://sjtu.feishu.cn/wiki/wikcnsbnAh5l1UIkUKyYTnz7q1c)
+ 配置好VSCode + Docker + Devcontainer插件后，进入`.devcontainer`文件夹，点击`Open Folder in Containers`即可自动配置好Docker
### Adjust the template to your needs
+ Use this repo as a templete.
+ Modify /ros/ros_example.cc and /app/app_example.cc and etc.


### Build and run the example
```
# Build with cmake
mkdir build
cd build
cmake ..
make
# Build with catkin_make
cd .. && mkdir -p catkin_ws/src
cp -r CppTemplates/ catkin_ws/src/
cd catkin_ws && catkin_make
# Run
./build/modules/example/module_example_test
roscore
./build/devel/lib/cpptemplates2/ros_example
```


## FAQ
## Related projects

详细文档请大家参考[链接](https://sjtu.feishu.cn/docx/Ns7ldBtpJoisyKxcY5Tc3rgSnJc)



