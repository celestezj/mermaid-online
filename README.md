# Mermaid在线渲染工具

这是一个简单而功能强大的Mermaid在线编辑和渲染工具，用于创建和可视化流程图、序列图、甘特图等图表。该工具使用纯HTML、CSS和JavaScript实现，无需后端服务，可以轻松部署在静态网站托管平台上。

## 功能特点

- **实时编辑与渲染**: 修改代码后自动渲染，也可以点击"立即渲染"按钮手动触发
- **左右分栏设计**: 左侧编辑区(30%)，右侧渲染区(70%)
- **交互式图表操作**:
  - 鼠标拖动移动图表
  - Ctrl+滚轮缩放图表
  - 放大/缩小按钮
  - 重置画布按钮
  - 全屏展示功能
- **响应式设计**: 适配不同屏幕尺寸
- **无依赖部署**: 只需一个HTML文件，引用CDN上的Mermaid库
- **URL参数共享**: 通过`?code=`参数自动填充图表源码，分享一条链接即可打开图表
- **一键复制分享链接**: 点击编辑器右上角"复制分享链接"按钮，生成当前图表的分享URL
- **离线版本**: 附带`offline_version/`目录，内置Mermaid库，完全离线可用

## 在线演示

访问[Mermaid在线渲染工具](https://mermaid-online.dymichina17.workers.dev/)体验该工具。

## 通过链接共享图表

工具支持URL参数`?code=`自动填入图表源码，方便分享，也可在其他网页中通过链接一键打开。

### 生成分享链接

1. 在编辑器中输入Mermaid源码
2. 点击编辑器右上角的**复制分享链接**按钮
3. 链接已复制到剪贴板，对方打开该链接即可看到图表

### 在其他网页中引用

在网页中添加一个链接，点击后在新标签页打开工具并自动渲染图表：

```html
<a href="https://mermaid-online.dymichina17.workers.dev/?code=你的源码URL编码" target="_blank">查看图表</a>
```

其中`?code=`的值是Mermaid源码经过`encodeURIComponent()`编码后的字符串，例如：

```
https://mermaid-online.dymichina17.workers.dev/?code=graph%20TD%0A%20%20A%5B开始%5D%20--%3E%20B%5B结束%5D
```

该功能是纯前端实现，部署到任何静态托管平台（Cloudflare Pages / Workers 等）均可使用。

## 本地使用

1. 克隆仓库:
```bash
git clone https://github.com/yourusername/mermaid-online-editor.git
```

2. 在浏览器中打开`index.html`文件即可使用。

## 在Cloudflare Pages上部署

### 方法1: 通过GitHub仓库部署

1. **确保代码已推送到GitHub**:
   确认你的项目代码(至少包含index.html)已经上传到GitHub仓库中。

2. **登录Cloudflare Dashboard**:
   访问[Cloudflare Dashboard](https://dash.cloudflare.com/)并登录你的账户。

3. **创建新的Pages项目**:
   - 在侧边栏找到并点击"Pages"
   - 点击"创建项目"按钮
   - 选择"Connect to Git"

4. **连接到GitHub仓库**:
   - 授权Cloudflare访问你的GitHub账户
   - 从列表中选择包含Mermaid编辑器代码的仓库

5. **配置部署设置**:
   - 构建设置保持默认即可，因为我们只有静态HTML文件
   - 构建命令可以留空
   - 构建输出目录使用默认值(`/`)或指定为仓库根目录

6. **部署项目**:
   - 点击"保存并部署"按钮
   - Cloudflare会自动构建并部署你的站点
   - 部署完成后，你会获得一个`*.pages.dev`格式的URL

### 方法2: 直接上传文件部署

1. **登录Cloudflare Dashboard**:
   访问[Cloudflare Dashboard](https://dash.cloudflare.com/)并登录。

2. **创建新的Pages项目**:
   - 在侧边栏找到并点击"Pages"
   - 点击"创建项目"按钮
   - 选择"Direct Upload"(直接上传)

3. **上传文件**:
   - 为项目命名
   - 将index.html文件拖放到上传区域
   - 点击"部署站点"按钮

4. **访问你的站点**:
   部署完成后，Cloudflare会提供一个`*.pages.dev`格式的URL，你可以通过该URL访问你的Mermaid在线渲染工具。

## 自定义域名(可选)

如果你想使用自定义域名而不是默认的`*.pages.dev`域名:

1. 在Cloudflare Pages项目设置中找到"自定义域"选项
2. 点击"设置自定义域"
3. 输入你的域名并按照提示完成DNS配置

## 更新部署

- **通过GitHub部署**: 只需将更改推送到GitHub仓库，Cloudflare会自动检测并重新部署
- **直接上传部署**: 在Cloudflare Pages控制台中重新上传文件进行更新

## 离线版本

`offline_version/`目录提供一个完全离线的版本，内置了Mermaid库文件，无需网络即可使用。

- 直接双击`offline_version/index.html`即可在浏览器中使用
- 部署时上传整个`offline_version/`目录
- 功能与在线版一致，同样支持`?code=`参数和分享链接

## 技术栈

- HTML5
- CSS3
- JavaScript
- [Mermaid.js](https://mermaid.js.org/) - 用于图表渲染

## 贡献

欢迎通过提交Pull Request或创建Issue来贡献代码或提出建议。

## 许可证

[MIT](LICENSE)

---

希望这个工具能够帮助你更高效地创建和分享各种图表！如有问题或建议，请通过GitHub Issues联系我。
