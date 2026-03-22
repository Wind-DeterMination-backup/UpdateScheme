# UpdateScheme

在线更新蓝图（schematic）的 Mindustry 客户端 Java 模组。

## v2 协议

- 不再使用 `PrivateBin`，也不再依赖回帖 / 盖楼式更新链。
- 每个版本正文直接上传到 `0x0.st`，作为不可变内容 blob。
- 可变清单（manifest）与作者索引存放在公开 GitHub 仓库中。
- 分享文本格式为：`UpdateScheme:v2:<owner/repo>:<manifestId>`
- 首次发布需要提供作者名，以及一个有仓库内容写权限的 GitHub Token。
- 若未填写 registry 仓库，模组会自动使用或创建 `<你的 GitHub 登录名>/UpdateSchemeRegistry`

## 使用说明

- 订阅时可直接粘贴 `UpdateScheme:v2:...` 分享文本，或 GitHub manifest 链接。
- 发布时会生成一个 manifest，并把当前蓝图版本绑定到该 manifest。
- 后续更新会写入同一个 manifest，订阅者只需要继续检查更新即可。
- 作者页会根据 GitHub 中保存的索引展示该作者已发布的蓝图列表。

## 构建

```bash
gradle deploy
```

产物输出：

- `dist/UpdateScheme.jar`
- `dist/UpdateScheme.zip`
- `../构建/UpdateScheme/UpdateScheme-<version>.jar`
- `../构建/UpdateScheme/UpdateScheme-<version>.zip`
