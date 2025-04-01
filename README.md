# <p align="center">URL Scheme Handler<p>

为 Windows 应用添加自定义 URL Scheme 以便从浏览器调用

## 🧱 下载



蓝奏云，密码 `5kl2`：[https://kutt.lckp.top/OdMR0G](https://kutt.lckp.top/OdMR0G)

## ✍️ 使用

1. 点击 `+ Add to Registry` 添加注册表
2. 点击 `+` 添加应用
3. 在左边输入框填写应用名称
4. 在右边选择需要调用的应用



建议添加 `开启勾选框` 注册表，添加后首次运行可勾选是否自动允许运行，后续不用再弹窗确认

开启勾选框：[Enable_ExternalProtocolDialog_ShowCheckbox.reg](https://github.com/LuckyPuppy514/url-scheme-handler/blob/main/reg/Enable_ExternalProtocolDialog_ShowCheckbox.reg)

移除勾选框：[Remove_ExternalProtocolDialog_ShowCheckbox.reg](https://github.com/LuckyPuppy514/url-scheme-handler/blob/main/reg/Remove_ExternalProtocolDialog_ShowCheckbox.reg)

蓝奏云，密码 `5kl2`：[https://kutt.lckp.top/OdMR0G](https://kutt.lckp.top/OdMR0G)

## ✍️ 用法

```text
ush://${app_name}?${gzip_args}
```

参考代码

```text
// @require                 https://lf26-cdn-tos.bytecdntp.com/cdn/expire-1-y/pako/2.0.4/pako.min.js
```

```javascript
function compress(str) {
    return btoa(String.fromCharCode(...pako.gzip(str)));
};

const app_name = 'MPV';
const args = [
    '"https://example.com/example.mp4"',
    '--force-media-title="URL Scheme Handler"'
];

window.open(`ush://${app_name}?${compress(args.join(' '))}`, '_self');
```

实际执行命令

```bat
app_path "https://example.com/example.mp4" --force-media-title="URL Scheme Handler"
```


