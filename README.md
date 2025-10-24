# Spring Boot File Manager

基于 Spring Boot 2.x + Java 8 的文件管理系统，支持：
- 文件：上传、删除、移动、重命名、列出
- 目录：创建、删除、移动、重命名
- 搜索：按名称、扩展名、路径片段（可扩展内容搜索）
- 使用 Java NIO (Path, Files, WatchService) 实现文件操作与增量索引

## 技术栈
- Java 8
- Spring Boot 2.7.x
- Thymeleaf
- Bootstrap 5
- Java NIO

## 快速开始
1. 修改 `application.yml` 中 `file.base-path` (默认 `./data`)
2. 执行:
   ```bash
   mvn spring-boot:run
   ```
3. 浏览器访问: http://localhost:8080/

## 功能说明
| 功能 | 描述 |
|------|------|
| 文件操作 | 上传 / 删除 / 重命名 / 移动 |
| 目录操作 | 创建 / 删除（可递归） / 重命名 / 移动 |
| 搜索 | 按文件名包含、扩展名、路径片段 |
| 索引 | 启动时全量构建 + WatchService 增量更新 |

## 搜索实现
内存索引：`nameIndex` / `extIndex` / `pathSegmentIndex`。后续可扩展内容索引（开启需限制文件大小与类型）。

## 后续可扩展
- 内容全文检索（Lucene/ES）
- 权限与用户体系
- 回收站（延迟删除）
- 批量压缩下载
- WebSocket 实时通知

## 目录结构
```
src/
  main/
    java/com/example/filemanager/
      controller/
      service/
      dto/
      exception/
      util/
      watcher/
      config/
    resources/
      templates/
      application.yml
  test/
docs/
data/
```

## 许可证
本项目采用 MIT License（详见 LICENSE）。