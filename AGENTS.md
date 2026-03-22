# AGENTS.md - UpdateScheme AI 工作指南

本目录用于开发 `UpdateScheme`（Mindustry Java 客户端模组）。

## 1) 项目目标与边界

- 项目名：`UpdateScheme`
- 类型：Mindustry **Java 客户端模组**（非服务端插件）
- 目标游戏版本：`minGameVersion: 154`
- 主入口：`updatescheme.UpdateSchemeMod`
- 入口配置文件：`mod.json`

约束：

- Java 8 兼容（`sourceCompatibility/targetCompatibility=1.8`）
- 不引入新三方库
- 文案统一走 bundle key，不写死 UI 字符串

## 2) 目录结构

- 入口类：`src/main/java/updatescheme/UpdateSchemeMod.java`
- 功能类：`src/main/java/updatescheme/features/...`
- 本地化：`src/main/resources/bundles/bundle.properties` 与 `bundle_zh_CN.properties`
- 模组元数据：`src/main/resources/mod.json`

## 3) 构建/发布工作流

必须保持以下命令可用：

- `gradle deploy`

`deploy` 产物要求：

- `UpdateScheme/dist/UpdateScheme.jar`
- `UpdateScheme/dist/UpdateScheme.zip`

并且每次构建后复制到工作区构建目录：

- 目录：`构建/UpdateScheme`
- 文件名：
  - `UpdateScheme-<version>.jar`
  - `UpdateScheme-<version>.zip`

## 4) 变更后必做检查

每次修改后至少执行：

1. `gradle classes`
2. `gradle deploy`
3. 确认 `dist` 与 `构建/UpdateScheme` 下产物存在且命名正确

命令操作请使用 PowerShell 7（`pwsh`）。
