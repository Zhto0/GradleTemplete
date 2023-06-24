# 一、Gradle介绍
Gradle是项目构建工具，在Android上的应用主要是帮助开发者更方便构建apk。

# 二、Gradle构建基础

相关文件及其组织关系：
```
GradleLab
├─build.gradle      根工程project配置文件，用于定义所有子模块公共的配置参数
├─gradle.properties 全局属性配置文件
├─local.properties： 用作项目的私有属性配置，例如 SDK 安装目录，一般不把 local.properties 加入版本控制。
├─gradlew
├─gradlew.bat       启动脚本
├─settings.gradle   工程初始化配置文件，确定哪些模块参与构建
├─gradle
|   ├─wrapper
|   |    ├─gradle-wrapper.jar
|   |    └gradle-wrapper.properties    gradle版本配置
├─app
|  ├─build.gradle    模块project配置文件, 定义子模块配置参数
```
## 生命周期：
- 初始化：执行settings.gradle文件，构建project组。
- 配置：执行所有build.gradle，构建task的拓扑图。
- 执行：按配置顺序执行task及其依赖task。