# Changelog

所有本项目的显著更改都将记录在此文件中;

格式基于 [Keep a Changelog](https://keepachangelog.com/zh-CN/1.0.0/),
并且本项目遵循 [语义化版本](https://semver.org/lang/zh-CN);

## [1.0.30] - 2026-11-14 11:14
### 适配
- 适配 npm 12:该版本起不再把未知 CLI 标志转成 `npm_config_*` 环境变量,直接报错;`release.bat`、
  `build.bat` 中受影响的调用改为环境变量形式;

### 修复
- `release.bat` 写 `version.json` 时由 `echo ... >` 改为 PowerShell 写入,消除 cmd 重定向默认注入的
  CRLF 与行尾空格,产物为 LF、无尾随空格;
- `release.bat` 生成 Release Notes 后统一规范为 LF;
- `release.bat` 生成自适应 evb 模板时把内容统一为 LF,模板换行不再随来源变化;
- `build.bat` 生成的构建日志在读取前统一规范为 LF,规范化失败则中断并清理;
- 上述三处 PowerShell 调用增加 `$ErrorActionPreference='Stop'`,读文件失败时中断退出,不再静默写出空文件;

### 文档
- `.gitattributes` 重写为“默认 LF + Windows 脚本 CRLF + 二进制”三段式,补齐 Qt 工程文件(`*.qrc`、`*.ui`、
  `*.ts`、`*.qm`、`*.evb`)与 VS 工程/中间产物扩展名;路径模式统一使用正斜杠;
- 项目内文本文件换行统一为 LF(不含 `.fetched/`、`include/spdlog/`、`httplib` 等第三方代码);
-
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

[unreleased]: https://github.com/OpenFlun/GH-DesktopToCN/compare/v1.0.30...HEAD
[1.0.30]: https://github.com/OpenFlun/GH-DesktopToCN/compare/v1.0.29...v1.0.30
[1.0.29]: https://github.com/OpenFlun/GH-DesktopToCN/compare/v1.0.28...v1.0.29
[1.0.28]: https://github.com/OpenFlun/GH-DesktopToCN/compare/v1.0.27...v1.0.28