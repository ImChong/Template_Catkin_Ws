# 1. catkin

- [1. catkin](#1-catkin)
  - [1.1. what is catkin](#11-what-is-catkin)
  - [1.2. catkin\_make 与 catkin build 的区别？](#12-catkin_make-与-catkin-build-的区别)

## 1.1. what is catkin
>
> [Conceptual Overview](http://wiki.ros.org/catkin/conceptual_overview)

## 1.2. catkin_make 与 catkin build 的区别？
>
> `catkin_make` 和 `catkin build` 是ROS中用于构建ROS工作空间的两种不同的命令，它们来自不同的catkin工具。下面是它们之间的主要区别：
>
> **来源**:
>
> - `catkin_make`: 这是原始的catkin构建工具，它基于顶层的CMakeLists.txt文件来构建整个工作空间。
> - `catkin build`: 它来自`catkin_tools`包，是一个新的并行、隔离的构建工具。
>
> **构建方式**:
>
> - `catkin_make`: 构建整个工作空间为一个CMake项目。所有的软件包都在同一个CMake上下文中被构建。
> - `catkin build`: 每个软件包都在它自己的CMake上下文中被构建，确保更好的隔离。这意味着每个软件包都被视为一个独立的项目。
>
> **并行化**:
>
> - `catkin_make`: 支持在一次构建中构建多个包，但它们共享同一个CMake上下文。
> - `catkin build`: 可以并行构建多个包，并且每个包都在其自己的隔离环境中。
>
> **构建空间**:
>
> - `catkin_make`: 所有的输出都进入同一个构建空间，例如 `build/` 目录。
> - `catkin build`: 每个软件包都有自己的构建空间，例如 `build/<package_name>/`。
>
> **灵活性**:
>
> - `catkin_make`: 对于简单的项目和新手来说更简单直接。
> - `catkin build`: 提供了更多的高级功能，如构建配置、工作空间配置等。
>
> **其他工具**:
>
> - `catkin_make`: 主要是`catkin_make`命令。
> - `catkin build`: 作为`catkin_tools`的一部分，还有其他的命令，如`catkin clean`、`catkin list`等。
>
> 总的来说，`catkin build`为ROS工作流提供了更高级和更灵活的构建选项。对于大型项目和那些需要更细粒度控制的开发者来说，`catkin build`可能是更好的选择。但对于新手和小型项目，`catkin_make`可能更简单易用。如果你决定使用`catkin build`，请确保已经安装了`catkin_tools`包。
