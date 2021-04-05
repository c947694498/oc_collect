# oc_collect

## 问题锦囊
### 修复FV-T919 BCM94360CD 网卡速率低 (其他网卡可尝试借鉴)
1. 加载博通网卡驱动 AirportBrcmFixup.kext [https://github.com/acidanthera/AirportBrcmFixup](https://github.com/acidanthera/AirportBrcmFixup)
2. 引导参数boot-args 添加 `brcmfx-country=#a` 修改国家/地区代码为全球 
3. 引导参数boot-args 添加 `bbrcmfx-aspm` 覆盖用于pci-aspm-default的值, 用于修改默认电源管理
4. 建议修改路由器wifi信道，参考值48，也可常识其他
4. 上述boot-args可改为DeviceProperties方式注入参数
