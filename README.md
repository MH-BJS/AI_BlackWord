# AI 使用环境术语百科

一个面向初学者的静态术语查询网站，重点解释代理网络、IP 与网络身份、账号环境、API 与模型接入等常见说法。

## 在线部署

本项目适合直接部署到 GitHub Pages。

## 当前版本

**v0.2.0**

### v0.2.0 更新

- 新增“黑话拆解”：可把一串术语按现有词库静态拆解，不调用 AI。
- 词条支持独立 URL，可直接复制并分享某个词条。
- 新增“术语性质”标签，区分技术概念、社区常用说法、容易被营销化的说法。
- 新增 ISP、ASN、SOCKS5、NAT、解锁 5 个词条。
- 新增“静态 IP vs 静态住宅”“原生 IP vs 纯净 IP”对比。
- 保留搜索、分类浏览、易混淆概念、学习路线和概念关系图。

## 文件

```text
index.html   网站页面与交互逻辑
data.json    词条、对比、学习路线与版本数据
README.md    项目说明与版本记录
```

## 本地预览

页面通过 `fetch("data.json")` 读取词库，因此不建议直接双击 `index.html`。

在仓库目录运行：

```bash
python -m http.server 8000
```

然后打开：

```text
http://localhost:8000
```

## GitHub Pages 部署

1. 进入仓库 `Settings -> Pages`。
2. `Source` 选择 `Deploy from a branch`。
3. Branch 选择 `main`。
4. Folder 选择 `/ (root)`。
5. 保存后等待 Pages 完成部署。

## 维护原则

新增术语时，尽量保持以下结构：

- `term`：词条名
- `aliases`：别名 / 英文名
- `category`：所属分类
- `difficulty`：1~3
- `summary`：一句话理解
- `what`：它是什么
- `why`：为什么会遇到
- `example`：真实 AI 场景例子
- `confuse`：容易混淆的词
- `prereq`：建议先了解的词
- `related`：继续了解
- `nature`：术语性质

内容原则：优先保证准确性；对于“原生、纯净、解锁、养号”等没有统一标准的社区说法，应明确提示其语境和局限，不把商家话术当成严格技术标准。

## 更新检查

每次发布前建议至少检查：

- [ ] 搜索能找到新词
- [ ] 关联词可点击
- [ ] 黑话拆解不会报错
- [ ] 手机端没有明显横向溢出
- [ ] `data.json` JSON 格式有效
- [ ] 词条中的关联词都存在
- [ ] GitHub Pages 部署成功
