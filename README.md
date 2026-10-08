# NanoPi R3S FriendlyWrt GitHub Actions

这是一个精简的 GitHub Actions 编译仓库，目标是：

- NanoPi R3S / RK3566
- 官方 FriendlyARM/FriendlyWrt 构建体系
- 默认 FriendlyWrt 25.12
- 可选择 24.10
- 只编译 R3S，不编译其他型号
- 不加入 OpenClash、插件或第三方修改
- 最终输出 `NanoPi-R3S-Series-FriendlyWrt-XX.XX.img.gz`

## 使用方法

1. 新建 GitHub 仓库。
2. 把本仓库中的 `.github` 文件夹和 `scripts` 文件夹上传到仓库根目录。
3. 打开仓库的 `Actions`。
4. 第一次如果提示启用 Actions，点击启用。
5. 点击 `Build NanoPi R3S FriendlyWrt`。
6. 点击 `Run workflow`。
7. 选择 `25.12`（默认）或 `24.10`。
8. 点击绿色的 `Run workflow`。
9. 等待编译完成。
10. 打开本次运行，在最下面的 `Artifacts` 下载 R3S 固件。

## 输出

`NanoPi-R3S-Series-FriendlyWrt-25.12.img.gz`

这个文件是 SD 卡/全量镜像用途。

官方 FriendlyWrt 文档说明 `.img.gz` 可以写入 SD 卡，也可作为 eMMC 全量刷机镜像。

## 注意

GitHub Actions 编译可能需要较长时间。该工作流给每次编译设置了 12 小时上限。

本仓库不保存 FriendlyWrt 源码；编译时会从 FriendlyARM 官方 manifest、kernel、u-boot、rkbin、device 和脚本仓库拉取源码。
