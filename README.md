# AI 使用环境术语百科

这是一个纯静态术语查询网站，适合部署到 GitHub Pages。

## 本地预览

因为页面通过 `fetch("data.json")` 读取词库，不建议直接双击 `index.html`。
在该目录运行一个简单静态服务器：

```bash
python -m http.server 8000
```

然后浏览器打开：

```text
http://localhost:8000
```

## GitHub Pages 部署

1. 新建一个 GitHub 仓库。
2. 上传 `index.html` 和 `data.json`。
3. 进入仓库 Settings → Pages。
4. Source 选择 Deploy from a branch。
5. 选择 `main` 分支和 `/ (root)`。
6. 保存后等待 GitHub 生成访问地址。

## 维护词条

所有词条都在 `data.json` 中。新增词条后无需修改页面结构。
