## 使用说明
在 Actions 选择该工作流手动点击 Run workflow 执行编译，等待固件编译完成上传至 releases 发布即可下载

### 配置说明
- 默认 LAN IP 已更改为 `192.168.10.1`，可在 `scripts/diy-part2.sh` 处修改


- 默认使用 52 MHz 闪存频率，52 MHz 下闪存读写速率相较 26 MHz 下翻倍，可达到 40MB/s 以上，**但部分机器因闪存体质差异，使用 52 MHz 闪存频率固件可能会出现 I/O 报错 (`dmesg | grep error` 查看)，无法正常使用，甚至可能无法启动**，你可以选择构建 26 MHz 闪存频率固件。

## 如何刷入

旧版 进入 uboot 需要手动设置本机 IP 192.168.1.100 网关 192.168.1.1 DNS 192.168.1.1，
新版 custom U-Boot 已支持 DHCP，浏览器输入 `192.168.1.1` 进入 Web-UI 刷写固件，
所有文件可在 https://firmware.download.immortalwrt.eu.org/uboot/mediatek 获取

## 注意事项
此分区布局默认不创建 eMMC 闪存最后一块 56G 大分区，你需要使用 `cfdisk /dev/mmcblk0` 为最后一块剩余空闲容量手动创建 /dev/mmcblk0p7 分区并通过 mkfs.ext4 格式化以挂载使用，此后更新刷入其他固件则无需再进行相同操作，固件可以自动挂载

## Credits
- [XiaoBinin/Actions-immortalwrt](https://github.com/XiaoBinin/Actions-immortalwrt)
- [ImmortalWrt](https://github.com/immortalwrt/immortalwrt)
- [hanwckf/immortalwrt-mt798x](https://github.com/hanwckf/immortalwrt-mt798x)
- [lgs2007m/immortalwrt-mt798x-rax3000m-emmc](https://github.com/lgs2007m/immortalwrt-mt798x-rax3000m-emmc)
- [GL-iNet](https://github.com/gl-inet)
- [padavanonly](https://github.com/padavanonly)
- [Microsoft Azure](https://azure.microsoft.com)
- [GitHub Actions](https://github.com/features/actions)
- [OpenWrt](https://github.com/openwrt/openwrt)
- [tmate](https://github.com/tmate-io/tmate)
- [mxschmitt/action-tmate](https://github.com/mxschmitt/action-tmate)
- [csexton/debugger-action](https://github.com/csexton/debugger-action)
- [Cowtransfer](https://cowtransfer.com)
- [WeTransfer](https://wetransfer.com/)
- [Mikubill/transfer](https://github.com/Mikubill/transfer)
- [softprops/action-gh-release](https://github.com/softprops/action-gh-release)
- [ActionsRML/delete-workflow-runs](https://github.com/ActionsRML/delete-workflow-runs)
- [dev-drprasad/delete-older-releases](https://github.com/dev-drprasad/delete-older-releases)
- [peter-evans/repository-dispatch](https://github.com/peter-evans/repository-dispatch)

## License

[MIT](https://github.com/P3TERX/Actions-OpenWrt/blob/main/LICENSE) © [**P3TERX**](https://p3terx.com)
