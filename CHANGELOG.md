# Changelog

所有本项目的显著更改都将记录在此文件中;

格式基于 [Keep a Changelog](https://keepachangelog.com/zh-CN/1.0.0/),
并且本项目遵循 [语义化版本](https://semver.org/lang/zh-CN);

## [1.0.29] - 2026-10-24

### 修复
- 修复自定义汉化入口提示框原始字符串提前终止导致的构建失败;
- 修复 release.bat 编译器缓存校验中构建目录重复拼接项目根、误判缓存变更的问题;
- 修复 release_template.evb 中两条 File 条目含换行导致封包报文件不存在的问题;

### 优化
- release.bat 封包前按当前项目根生成临时 evb 模板,install 路径随项目移动自适应;
- build.bat 增加项目目录变更检测,与 release.bat 行为对齐,不再依赖 cmake 输出文本匹配;
- build.bat 初始化 PATH_CHANGED 变量,避免脚本被复用时残留上一轮状态;

## [1.0.28] - 2026-10-24 11:42

### 优化
- 项目标点已改为以英文标点为主;
- 行宽改为以 123 为主,部分超宽表格改为了列表;

## [1.0.27] - 2026-08-11 11:03
### 添加
- 添加了一些缺失的映射;

[unreleased]: https://github.com/OpenFlun/GH-DesktopToCN/compare/v1.0.29...HEAD
[1.0.29]: https://github.com/OpenFlun/GH-DesktopToCN/compare/v1.0.28...v1.0.29
[1.0.28]: https://github.com/OpenFlun/GH-DesktopToCN/compare/v1.0.27...v1.0.28
[1.0.27]: https://github.com/OpenFlun/GH-DesktopToCN/compare/v1.0.26...v1.0.27