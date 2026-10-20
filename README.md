# developer-kits

开发环境常用安装包与工具集中存放仓库，便于团队成员下载与复用。

## 仓库说明

- 远程地址：`git@gitcode.com:liushuo_fe/developer-kits.git`
- 超过 **100MB** 的文件使用 **Git LFS（大文件存储）**；不超过 100MB 的文件使用普通 Git 提交。
- 克隆或拉取前请先安装 [Git LFS](https://git-lfs.com/)，否则大文件可能只下到指针文件。

```bash
git lfs install
git clone git@gitcode.com:liushuo_fe/developer-kits.git
```

若已克隆但大文件未展开：

```bash
git lfs pull
```

## 文件清单

| 文件 | 说明 | 约大小 | 存储方式 |
|------|------|--------|----------|
| `Git-2.39.2-32-bit.exe` | Git 2.39.2 Windows 32 位安装程序 | 51 MB | 普通 Git |
| `nvm-setup.exe` | nvm-windows 安装程序（Node 版本管理） | 5 MB | 普通 Git |
| `nacos-server-2.0.1.zip` | Nacos Server 2.0.1 | 112 MB | Git LFS |
| `navicat18_premium_lite_cs_x64.exe` | Navicat 18 Premium Lite（简体中文 x64） | 161 MB | Git LFS |
| `OpenJDK17U-jdk_x64_windows_hotspot_17.0.20.1_1.msi` | Eclipse Temurin OpenJDK 17（Windows x64） | 161 MB | Git LFS |

## 使用提示

1. **Git**：运行 `Git-2.39.2-32-bit.exe` 安装；若本机为 64 位系统，可按需自行改用官方 64 位安装包。
2. **nvm**：运行 `nvm-setup.exe`，安装后可用 `nvm install` / `nvm use` 管理 Node.js 版本。
3. **Nacos**：解压 `nacos-server-2.0.1.zip` 后，按官方文档启动（常见为 `bin/startup.cmd` 或 `bin/startup.sh`）。
4. **Navicat**：运行对应 `.exe` 安装。
5. **OpenJDK 17**：运行 `.msi` 安装；安装后可用 `java -version` 确认。

## 新增大文件约定

新增安装包时：

- **≤ 100MB**：直接 `git add` 后提交推送。
- **> 100MB**：先在 `.gitattributes` 中为该文件添加 LFS 规则，再提交推送。示例：

```gitattributes
your-large-file.zip filter=lfs diff=lfs merge=lfs -text
```

## License（许可证）

本仓库仅作内部工具分发与备份用途。各安装包的版权与许可条款归其原作者 / 发行方所有，使用前请遵守对应软件的许可协议。
