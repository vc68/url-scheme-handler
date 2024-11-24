# <p align="center">URL Scheme Handler<p>

快速为 Windows 应用添加 URL Scheme 以便从浏览器打开外部程序

## 下载

[releases](https://github.com/LuckyPuppy514/url-scheme-handler/releases)

[蓝奏云](https://kutt.lckp.top)

## 安装

以 **管理员** 身份运行 `url-scheme-handler.exe`

### 1. 添加注册表

点击 `Add to Registry` 添加注册表

### 2. 添加应用并保存

点击 `+` 添加应用，输入应用名称，选择对应的可执行程序后点击 `Save` 保存

## 使用

```text
ush://${app_name}?${gzip_args}
```

调用例子

```javascript
function compress(str) {
    return btoa(String.fromCharCode(...pako.gzip(str)));
}

const appName = 'MPV';

const media = {
    video: 'https://example.com/1.mp4',
    title: 'URL Scheme Handler',
}

let args = [
    `"${media.video}"`,
    `--force-media-title="${media.title}"`,
]
args = args.filter(item => item !== '');

window.open(`ush://${appName}?${compress(args.join(' '))}`, '_self');
```

实际执行命令

```bat
app_path "https://example.com/1.mp4" --force-media-title="URL Scheme Handler"
```
